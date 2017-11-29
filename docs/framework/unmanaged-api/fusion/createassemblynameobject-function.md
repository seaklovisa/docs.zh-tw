---
title: "CreateAssemblyNameObject 函式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type: DLLExport
f1_keywords: CreateAssemblyNameObject
helpviewer_keywords: CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 8281c7944ff96110145a6f5c43a0a0e7da58fdcf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="ae953-102">CreateAssemblyNameObject 函式</span><span class="sxs-lookup"><span data-stu-id="ae953-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="ae953-103">取得的介面指標[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)執行個體，表示具有指定名稱的組件的唯一識別。</span><span class="sxs-lookup"><span data-stu-id="ae953-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae953-104">語法</span><span class="sxs-lookup"><span data-stu-id="ae953-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ae953-105">參數</span><span class="sxs-lookup"><span data-stu-id="ae953-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="ae953-106">[out]傳回`IAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="ae953-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="ae953-107">[in]若要建立新的組件名稱`IAssemblyName`執行個體。</span><span class="sxs-lookup"><span data-stu-id="ae953-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="ae953-108">[in]要傳遞給物件建構函式的旗標。</span><span class="sxs-lookup"><span data-stu-id="ae953-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="ae953-109">[in]保留供未來擴充。</span><span class="sxs-lookup"><span data-stu-id="ae953-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="ae953-110">`pvReserved`必須是 null 參考。</span><span class="sxs-lookup"><span data-stu-id="ae953-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae953-111">需求</span><span class="sxs-lookup"><span data-stu-id="ae953-111">Requirements</span></span>  
 <span data-ttu-id="ae953-112">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae953-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae953-113">**標頭：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="ae953-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ae953-114">**程式庫：**包含做為 MsCorEE.dll 中的資源</span><span class="sxs-lookup"><span data-stu-id="ae953-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ae953-115">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae953-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae953-116">另請參閱</span><span class="sxs-lookup"><span data-stu-id="ae953-116">See Also</span></span>  
 [<span data-ttu-id="ae953-117">IAssemblyName 介面</span><span class="sxs-lookup"><span data-stu-id="ae953-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="ae953-118">融合全域靜態函式</span><span class="sxs-lookup"><span data-stu-id="ae953-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)