---
title: "ICorDebugILFrame2::EnumerateTypeParameters 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame2.EnumerateTypeParameters
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame2::EnumerateTypeParameters
helpviewer_keywords:
- EnumerateTypeParameters method, ICorDebugILFrame2 interface [.NET Framework debugging]
- ICorDebugILFrame2::EnumerateTypeParameters method [.NET Framework debugging]
ms.assetid: 722d0d74-e0df-491f-98c4-62d501dfaf6f
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ebc2496d633c04c94e94be201956daab38b79224
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframe2enumeratetypeparameters-method"></a><span data-ttu-id="7c6a1-102">ICorDebugILFrame2::EnumerateTypeParameters 方法</span><span class="sxs-lookup"><span data-stu-id="7c6a1-102">ICorDebugILFrame2::EnumerateTypeParameters Method</span></span>
<span data-ttu-id="7c6a1-103">取得包含 ICorDebugTypeEnum 物件<xref:System.Type>這個框架中的參數。</span><span class="sxs-lookup"><span data-stu-id="7c6a1-103">Gets an ICorDebugTypeEnum object that contains the <xref:System.Type> parameters in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c6a1-104">語法</span><span class="sxs-lookup"><span data-stu-id="7c6a1-104">Syntax</span></span>  
  
```  
HRESULT EnumerateTypeParameters (  
    [out] ICorDebugTypeEnum    **ppTyParEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c6a1-105">參數</span><span class="sxs-lookup"><span data-stu-id="7c6a1-105">Parameters</span></span>  
 `ppTyParEnum`  
 <span data-ttu-id="7c6a1-106">ICorDebugTypeEnum 介面物件，可讓列舉型別參數的位址指標。</span><span class="sxs-lookup"><span data-stu-id="7c6a1-106">A pointer to the address of a ICorDebugTypeEnum interface object that allows enumeration of type parameters.</span></span>  
  
 <span data-ttu-id="7c6a1-107">型別參數的清單中包含的類別型別參數 （如果有的話） 後面的方法型別參數 （如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="7c6a1-107">The list of type parameters include the class type parameters (if any) followed by the method type parameters (if any).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7c6a1-108">備註</span><span class="sxs-lookup"><span data-stu-id="7c6a1-108">Remarks</span></span>  
 <span data-ttu-id="7c6a1-109">使用[imetadataimport2:: Enumgenericparams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)方法來判斷多少類別型別參數和方法包含的類型的參數清單。</span><span class="sxs-lookup"><span data-stu-id="7c6a1-109">Use the [IMetaDataImport2::EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md) method to determine how many class type parameters and method type parameters this list contains.</span></span>  
  
 <span data-ttu-id="7c6a1-110">型別參數並非永遠可用。</span><span class="sxs-lookup"><span data-stu-id="7c6a1-110">The type parameters are not always available.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c6a1-111">需求</span><span class="sxs-lookup"><span data-stu-id="7c6a1-111">Requirements</span></span>  
 <span data-ttu-id="7c6a1-112">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c6a1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c6a1-113">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c6a1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c6a1-114">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c6a1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c6a1-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c6a1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>