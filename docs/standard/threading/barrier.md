---
title: 屏障 (.NET Framework)
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- synchronization primitives, Barrier
ms.assetid: 613a8bc7-6a28-4795-bd6c-1abd9050478f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 864571262d1c9c060235840424542856187341df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33584294"
---
# <a name="barrier-net-framework"></a>屏障 (.NET Framework)
「屏障」是一種使用者定義的同步處理原始物件，可讓多個執行緒 (也稱為「參與者」) 以並行方式分階段處理演算法。 每個參與者都會執行，直到它到達程式碼中的屏障點為止。 屏障代表一個工作階段的結束。 當參與者到達屏障時，它就會封鎖，直到所有參與者都到達相同的屏障為止。 在所有參與者都到達屏障之後，您就可以選擇性地叫用階段後動作。 當所有其他執行緒仍然處於封鎖狀態時，單一執行緒可以使用這個階段後動作來執行動作。 執行這個動作之後，這些參與者都會解除封鎖。  
  
 下列程式碼片段示範基本屏障模式。  
  
 [!code-csharp[CDS_Barrier#02](../../../samples/snippets/csharp/VS_Snippets_Misc/cds_barrier/cs/barrier.cs#02)]
 [!code-vb[CDS_Barrier#02](../../../samples/snippets/visualbasic/VS_Snippets_Misc/cds_barrier/vb/barrier_vb.vb#02)]  
  
 如需完整的範例，請參閱[如何：使用屏障同步處理並行作業](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)。  
  
## <a name="adding-and-removing-participants"></a>加入和移除參與者  
 當您建立 <xref:System.Threading.Barrier> 時，請指定參與者的數目。 您也可以隨時以動態方式加入或移除參與者。 例如，如果某個參與者解決了自己那部分的問題，您就能儲存結果、停止該執行緒上的執行，並呼叫 <xref:System.Threading.Barrier.RemoveParticipant%2A> 以減少屏障中的參與者數目。 當您透過呼叫 <xref:System.Threading.Barrier.AddParticipant%2A> 來加入參與者時，傳回值就會指定目前的階段編號，而這個編號可用於初始化新參與者的工作。  
  
## <a name="broken-barriers"></a>中斷的屏障  
 如果某個參與者無法到達屏障，可能會發生死結。 若要避免這些死結，請使用 <xref:System.Threading.Barrier.SignalAndWait%2A> 方法的多載來指定逾時期限和取消語彙基元。 這些多載會先傳回每個參與者可檢查的布林值，然後再繼續進行下一個階段。  
  
## <a name="post-phase-exceptions"></a>階段後例外狀況  
 如果階段後委派擲回例外狀況，它就會包裝在 <xref:System.Threading.BarrierPostPhaseException> 物件中，然後傳播給所有參與者。  
  
## <a name="barrier-versus-continuewhenall"></a>屏障與 ContinueWhenAll 的比較  
 當執行緒在迴圈中執行多個階段時，屏障會特別有用。 如果您的程式碼只需要一個或兩個工作階段，請考慮是否要使用 <xref:System.Threading.Tasks.Task?displayProperty=nameWithType> 物件搭配任何一種隱含聯結，包括：  
  
-   <xref:System.Threading.Tasks.TaskFactory.ContinueWhenAll%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.Invoke%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.ForEach%2A>  
  
-   <xref:System.Threading.Tasks.Parallel.For%2A>  
  
 如需詳細資訊，請參閱[使用接續工作鏈結工作](../../../docs/standard/parallel-programming/chaining-tasks-by-using-continuation-tasks.md)。  
  
## <a name="see-also"></a>請參閱  
 [執行緒物件和功能](../../../docs/standard/threading/threading-objects-and-features.md)  
 [操作說明：使用屏障同步處理並行作業](../../../docs/standard/threading/how-to-synchronize-concurrent-operations-with-a-barrier.md)
