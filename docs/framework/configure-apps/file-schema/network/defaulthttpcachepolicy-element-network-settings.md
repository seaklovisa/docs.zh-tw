---
title: '&lt;defaultHttpCachePolicy&gt;項目 （網路設定）'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/requestCaching/defaultHttpCachePolicy
- http://schemas.microsoft.com/.NetConfiguration/v2.0#defaultHttpCachePolicy
helpviewer_keywords:
- defaultHttpCachePolicy element
- <defaultHttpCachePolicy> element
ms.assetid: 2c1247d0-39b0-4c12-919a-a925ce075c79
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: 0425711687a2f8b40f2c645e1c478d52b56ad979
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/03/2018
ms.locfileid: "32741837"
---
# <a name="ltdefaulthttpcachepolicygt-element-network-settings"></a>&lt;defaultHttpCachePolicy&gt;項目 （網路設定）
說明 HTTP 快取是否作用中，並且描述預設的快取原則。  
  
 \<configuration>  
\<system.net>  
\<requestCaching >  
\<defaultHttpCachePolicy >  
  
## <a name="syntax"></a>語法  
  
```xml  
<defaultHttpCachePolicy  
  policyLevel="BypassCache|Default"  
  minimumFresh="d.hh:mm:ss|minValue|maxValue"  
  maximumAge="d.hh:mm:ss|minValue|maxValue"  
  maximumStale="d.hh:mm:ss|minValue|maxValue"  
/>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
  
|屬性|描述|  
|---------------|-----------------|  
|`maximumAge`|快取的物件標示為已過期之前，請指定最大時間間隔。|  
|`maximumStale`|指定的最長的時間超過快取的物件標示為已過期之前所計算的有效期限時間。|  
|`minimumFresh`|指定要視為有效的快取物件的最小時間。|  
|`policyLevel`|指定是否快取的原則會自動進行，或是否略過快取。 預設值是 `BypassCache`。|  
  
### <a name="child-elements"></a>子項目  
 無  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|[requestCaching](../../../../../docs/framework/configure-apps/file-schema/network/requestcaching-element-network-settings.md)|控制網路要求的快取機制。|  
  
## <a name="remarks"></a>備註  
 值`policyLevel`屬性是`BypassCache`或`Default`。  
  
 值`maximumAge`， `maximumStale`，和`minimumFresh`項目所使用的格式的其中一個明確的時間間隔*d*。*hh*:*公釐*:*ss* （天數、 時、 分、 秒為單位），或常數`minValue`或`maxValue`視情況。  
  
## <a name="configuration-files"></a>組態檔  
 此項目可以用於應用程式組態檔或電腦組態檔 (Machine.config)。  
  
## <a name="example"></a>範例  
 下列範例會示範如何指定新的最小時間，為六小時，最長使用期限時間為兩天和四個小時的最長過時時間。  
  
```xml  
<configuration>  
  <system.net>  
    <requestCaching>  
      <defaultHttpCachePolicy  
        minimumFresh="0.06:00:00"  
        maximumAge="2.00:00:00"  
        maximumStale="0.04:00:00"
      />  
    </requestCaching>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.Net.Cache>  
 <xref:System.Net.WebRequest>  
 <xref:System.Net.Cache.RequestCacheLevel>  
 [網路設定結構描述](../../../../../docs/framework/configure-apps/file-schema/network/index.md)
