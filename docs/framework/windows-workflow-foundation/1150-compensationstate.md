---
title: 1150 - CompensationState
ms.date: 03/30/2017
ms.assetid: eb015842-cc5a-47be-bce5-6af39e567723
ms.openlocfilehash: 61613a27c4d4d8fb0b206246fef25ae87def47a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
---
# <a name="1150---compensationstate"></a>1150 - CompensationState
## <a name="properties"></a>屬性  
  
|||  
|-|-|  
|ID|1150|  
|關鍵字|WFActivities|  
|層級|資訊|  
|通道|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>描述  
 表示 CompensableActivity 中的狀態變更。  
  
## <a name="message"></a>訊息  
 CompensableActivity '%1' 處於 '%2' 狀態。  
  
## <a name="details"></a>詳細資料  
  
|資料項目名稱|資料項目型別|描述|  
|--------------------|--------------------|-----------------|  
|DisplayName|xs:string|活動的顯示名稱。|  
|狀態|xs:string|補償狀態。|  
|AppDomain|xs:string|由 AppDomain.CurrentDomain.FriendlyName 傳回的字串。|
