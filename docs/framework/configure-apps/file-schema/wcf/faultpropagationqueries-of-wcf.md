---
title: WCF 的 &lt;faultPropagationQueries&gt;
ms.date: 03/30/2017
ms.assetid: d85f66a7-e7b0-4dbb-83cc-89fa06fc9161
ms.openlocfilehash: 5db043b5d4d150628df386dafb6e7bd351a0a28a
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
ms.locfileid: "32753998"
---
# <a name="ltfaultpropagationqueriesgt-of-wcf"></a>WCF 的 &lt;faultPropagationQueries&gt;
代表查詢的集合，這些查詢可用來追蹤活動內發生之錯誤的處理。  每當 FaultHandler 處理錯誤時，都會發生這個事件。 您應該使用這種查詢來追蹤活動中發生的錯誤處理。 追蹤參與者必須要具備查詢，才能訂閱錯誤傳播記錄。  
  
 如需追蹤設定檔查詢的詳細資訊，請參閱[追蹤設定檔](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)。  
  
 \<system.serviceModel>  
\<追蹤 >  
\<trackingProfile>  
\<工作流程 >  
\<faultPropagationQueries >  
  
## <a name="syntax"></a>語法  
  
```xml
<tracking>   <trackingProfile name="Name">       <workflow>          <faultPropagationQueries>             <faultPropagationQuery activityName="String"                 faultHandlerActivityName="String"/>          </faultPropagationQueries>       </workflow>   </trackingProfile></tracking>  
```

## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
 無。  
  
### <a name="child-elements"></a>子項目  
  
|項目|描述|  
|-------------|-----------------|  
|[\<faultPropagationQuery >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/faultpropagationquery.md)|用來追蹤活動中發生之錯誤處理的查詢。  每當 FaultHandler 處理錯誤時，都會發生這個事件。|  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|[\<工作流程 >](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflow.md)|包括特定工作流程之所有查詢的組態項目，這個工作流程可由 `activityDefinitionId` 屬性識別。|  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElementCollection?displayProperty=nameWithType>       
 <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>       
 [工作流程追蹤及追蹤](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)  
 [追蹤設定檔](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
