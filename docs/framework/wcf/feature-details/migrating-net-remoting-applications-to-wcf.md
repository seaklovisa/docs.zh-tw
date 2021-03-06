---
title: 將 .NET 遠端處理應用程式移轉到 WCF
ms.date: 03/30/2017
helpviewer_keywords:
- ',NET remoting [WCF]'
ms.assetid: 24793465-65ae-4308-8c12-dce4fd12a583
ms.openlocfilehash: 53f63352503a48ee849580e676b5fe98f3dcf2cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33492492"
---
# <a name="migrating-net-remoting-applications-to-wcf"></a>將 .NET 遠端處理應用程式移轉到 WCF
**本主題專門說明一項為了在現有應用程式中提供回溯相容性而保留的舊有技術，不建議用於新的開發工作。分散式應用程式現在應該使用 WCF 加以開發。**  
  
 有兩種方式可利用 WCF 與現有的.NET 遠端處理應用程式： 整合與移轉。 整合可讓您有.Net Remoting 2.0 和 WCF 執行並存，讓您的相同商務物件這兩個同時公開技術而不需要修改現有的.Net Remoting 2.0 程式碼。 整合需要在 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 2.0 (含) 以上版本執行。 如果您想要利用 WCF 功能並不需要與 Remoting 2.0 系統的網路相容性，您可以將整個服務移轉至 WCF。 從.NET Remoting 2.0 移轉至 WCF 需要變更遠端物件的介面和其組態設定。 這兩個主題中涵蓋[從遠端處理到 Windows Communication Foundation](http://go.microsoft.com/fwlink/?LinkId=74403)。  
  
## <a name="see-also"></a>另請參閱  
 [概念性概觀](../../../../docs/framework/wcf/conceptual-overview.md)
