---
title: 4211 - QueuingSqlRetry
ms.date: 03/30/2017
ms.assetid: df569f88-c86b-4503-840d-1399b67f4df7
ms.openlocfilehash: ede74eb642c5c2c79b90cf1458db424d9f83b087
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33514565"
---
# <a name="4211---queuingsqlretry"></a>4211 - QueuingSqlRetry
## <a name="properties"></a>屬性  
  
|||  
|-|-|  
|ID|4211|  
|關鍵字|WFInstanceStore|  
|層級|警告|  
|通道|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>描述  
 表示佇列 SQL 重試。  
  
## <a name="message"></a>訊息  
 佇列 SQL 重試，但延遲 %1 毫秒。  
  
## <a name="details"></a>詳細資料  
  
|資料項目名稱|資料項目型別|描述|  
|--------------------|--------------------|-----------------|  
|延遲|xs:string|重試之間的延遲。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 傳回的字串。|
