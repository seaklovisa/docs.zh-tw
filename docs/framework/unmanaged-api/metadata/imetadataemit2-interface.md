---
title: IMetaDataEmit2 介面
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2
helpviewer_keywords:
- IMetaDataEmit2 interface [.NET Framework metadata]
ms.assetid: 866dc96b-bbfc-4c0f-80c2-38ce93072106
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 418e5287852b1a8d69d310d2ba71e4f2a3b5d7bd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/04/2018
ms.locfileid: "33449227"
---
# <a name="imetadataemit2-interface"></a>IMetaDataEmit2 介面
擴充[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)介面主要是為了讓您能夠使用泛型型別。  
  
## <a name="methods"></a>方法  
  
|方法|描述|  
|------------|-----------------|  
|[DefineGenericParam 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definegenericparam-method.md)|建立泛型類型參數，並取得該泛型型別參數的語彙基元。|  
|[DefineMethodSpec 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-definemethodspec-method.md)|建立泛型方法的執行個體，並取得定義的語彙基元。|  
|[GetDeltaSaveSize 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-getdeltasavesize-method.md)|取得值，指出資料來表示目前的編輯後繼續工作階段所做的變更所需的大小差異。|  
|[ResetENCLog 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-resetenclog-method.md)|重設為 編輯後繼續的記錄檔，並啟動新的工作階段。|  
|[SaveDelta 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedelta-method.md)|將目前的編輯後繼續工作階段的變更儲存至指定的檔案。|  
|[SaveDeltaToMemory 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatomemory-method.md)|將目前的編輯後繼續工作階段的變更儲存至記憶體。|  
|[SaveDeltaToStream 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-savedeltatostream-method.md)|指定的資料流從目前的編輯後繼續工作階段儲存變更。|  
|[SetGenericParamProps 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-setgenericparamprops-method.md)|設定指定的語彙基元所參考的泛型參數定義的屬性值。|  
  
## <a name="requirements"></a>需求  
 **平台：** 看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。  
  
 **標頭：** Cor.h  
  
 **程式庫：** 做為 MsCorEE.dll 中的資源  
  
 **.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>另請參閱  
 [中繼資料介面](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataEmit 介面](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
