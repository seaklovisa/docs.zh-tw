---
title: '&lt;identity&gt;'
ms.date: 03/30/2017
ms.assetid: c1d2ae56-e231-4a07-9c3f-9f13381dc0d8
ms.openlocfilehash: 1fc47b9595f409cf375dc75f2bf43e83f58491df
ms.sourcegitcommit: 9e18e4a18284ae9e54c515e30d019c0bbff9cd37
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/28/2018
ms.locfileid: "37071288"
---
# <a name="ltidentitygt"></a>&lt;identity&gt;
身分識別項目允許用戶端開發人員在設計階段指定服務的預期身分識別。 在用戶端與服務之間的交握程序，Windows Communication Foundation (WCF) 基礎結構可確保預期的服務符合這個元素的值的識別，因此可以進行驗證。 如需詳細資訊，請參閱[服務識別和驗證](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)。  
  
 \<system.ServiceModel>  
\<用戶端 >  
\<端點 >  
  
## <a name="syntax"></a>語法  
  
```xml  
<identity>  
    <certificate encodedValue="String"/>  
    <certificateReference findValue="String"   
       isChainIncluded="Boolean"  
       storeName="AddressBook/AuthRoot/CertificateAuthority/Disallowed/My/Root/TrustedPeople/TrustedPublisher"storeName="  
       storeLocation="LocalMachine/CurrentUser"  
       X509FindType= Enumeration./>  
    <dns value="String"/>  
    <rsa value="String"/>  
    <servicePrincipalName value="String"/>  
    <usePrincipalName value="String"/>  
</identity>  
```  
  
## <a name="attributes-and-elements"></a>屬性和項目  
 下列各節描述屬性、子項目和父項目。  
  
### <a name="attributes"></a>屬性  
 無。  
  
### <a name="child-elements"></a>子元素  
  
|項目|描述|  
|-------------|-----------------|  
|certificate|指定 X.509 憑證的設定。 此項目的型別為 <xref:System.ServiceModel.Configuration.CertificateElement>。 它包含是字串的屬性 `encodedValue`，指定由此憑證編碼的值。|  
|certificateReference|指定 X.509 憑證驗證的設定。 此項目的型別為 <xref:System.ServiceModel.Configuration.CertificateReferenceElement>。|  
|dns|指定用來驗證服務之 X.509 憑證的 DNS。 這個項目包含是字串的屬性 `value`，而且包含實際的身分識別。|  
|rsa|指定 X.509 憑證的 RSA 欄位值，此憑證可用來驗證用戶端的服務。 這個項目包含是字串的屬性 `value`，而且包含實際的身分識別。|  
|servicePrincipalName|指定伺服器主要名稱 (SPN) 身分識別，也就是用戶端可唯一識別服務執行個體時所用的主要名稱。 這個項目包含是字串的屬性 `value`，而且包含實際的主要名稱。 此項目的型別為 <xref:System.ServiceModel.Configuration.ServicePrincipalNameElement>。|  
|userPrincipalName|指定使用者主要名稱 (UPN) 身分識別，也就是網路上使用者的登入名稱類型。 使用者主要名稱包含 Active Directory，後面接著中使用的使用者物件名稱 at 符號 (\@)，然後通常是網域名稱系統父系網域。 例如，Fabrikam.com 網域樹狀目錄中的 Jeff 可能會有使用者主要名稱[ jeff@fabrikam.com ](mailto:jeffsmith@fabrikam.com)。  這個項目包含是字串的屬性 `value`，而且包含實際的主要名稱。 此項目的型別為 <xref:System.ServiceModel.Configuration.UserPrincipalNameElement>。|  
  
### <a name="parent-elements"></a>父項目  
  
|項目|描述|  
|-------------|-----------------|  
|[\<custom>](../../../../../docs/framework/configure-apps/file-schema/wcf/custom.md)|指定 netPeerTcpBinding 的自訂對等解析程式。|  
|[\<端點 >](http://msdn.microsoft.com/library/13aa23b7-2f08-4add-8dbf-a99f8127c017)|設定不同類型的端點。|  
|[\<issuer>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuer.md)|指定聯合服務的安全性權杖服務 (STS)。|  
|[\<issuerMetadata>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuermetadata.md)|為聯合服務的安全性權杖服務 (STS) 指定中繼資料端點。|  
|[\<issuedTokenParameters>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|定義自訂繫結中已發行權杖的參數。|  
|[\<localIssuer>](../../../../../docs/framework/configure-apps/file-schema/wcf/localissuer.md)|指定本機安全性權杖服務 (STS)。|  
  
## <a name="see-also"></a>另請參閱  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 [服務身分識別和驗證](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [端點：位址、繫結和合約](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
