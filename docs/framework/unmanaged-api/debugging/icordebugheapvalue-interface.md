---
title: ICorDebugHeapValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue
helpviewer_keywords: ICorDebugHeapValue interface [.NET Framework debugging]
ms.assetid: 1bca66db-0359-4ae8-846e-e35f7e547e8b
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7868fc84ba3003909992334d1a66e1ed243eca18
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugheapvalue-interface1"></a><span data-ttu-id="53c9a-102">ICorDebugHeapValue Interface1</span><span class="sxs-lookup"><span data-stu-id="53c9a-102">ICorDebugHeapValue Interface1</span></span>
<span data-ttu-id="53c9a-103">「 ICorDebugValue 」 表示已由 common language runtime (CLR) 記憶體回收行程回收之物件的子類別。</span><span class="sxs-lookup"><span data-stu-id="53c9a-103">A subclass of "ICorDebugValue" that represents an object that has been collected by the common language runtime (CLR) garbage collector.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="53c9a-104">方法</span><span class="sxs-lookup"><span data-stu-id="53c9a-104">Methods</span></span>  
  
|<span data-ttu-id="53c9a-105">方法</span><span class="sxs-lookup"><span data-stu-id="53c9a-105">Method</span></span>|<span data-ttu-id="53c9a-106">說明</span><span class="sxs-lookup"><span data-stu-id="53c9a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="53c9a-107">CreateRelocBreakpoint 方法</span><span class="sxs-lookup"><span data-stu-id="53c9a-107">CreateRelocBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-createrelocbreakpoint-method.md)|<span data-ttu-id="53c9a-108">未實作。</span><span class="sxs-lookup"><span data-stu-id="53c9a-108">Not implemented.</span></span>|  
|[<span data-ttu-id="53c9a-109">IsValid 方法</span><span class="sxs-lookup"><span data-stu-id="53c9a-109">IsValid Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue-isvalid-method.md)|<span data-ttu-id="53c9a-110">取得值，指出物件是否表示由此`ICorDebugHeapValue`有效，或已經由記憶體回收行程回收。</span><span class="sxs-lookup"><span data-stu-id="53c9a-110">Gets a value that indicates whether the object represented by this `ICorDebugHeapValue` is valid, or has been reclaimed by the garbage collector.</span></span> <span data-ttu-id="53c9a-111">.NET Framework 2.0 版中，這個方法已被取代。</span><span class="sxs-lookup"><span data-stu-id="53c9a-111">This method has been deprecated in the .NET Framework version 2.0.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="53c9a-112">備註</span><span class="sxs-lookup"><span data-stu-id="53c9a-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="53c9a-113">這個介面不支援跨電腦或跨處理序的遠端呼叫。</span><span class="sxs-lookup"><span data-stu-id="53c9a-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53c9a-114">需求</span><span class="sxs-lookup"><span data-stu-id="53c9a-114">Requirements</span></span>  
 <span data-ttu-id="53c9a-115">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53c9a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53c9a-116">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="53c9a-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="53c9a-117">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="53c9a-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="53c9a-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53c9a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c9a-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="53c9a-119">See Also</span></span>  
    
    
    
 [<span data-ttu-id="53c9a-120">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="53c9a-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)