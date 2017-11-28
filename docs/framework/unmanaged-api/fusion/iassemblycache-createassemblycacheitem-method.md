---
title: "IAssemblyCache::CreateAssemblyCacheItem 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAssemblyCache.CreateAssemblyCacheItem
api_location: fusion.dll
api_type: COM
f1_keywords: IAssemblyCache::CreateAssemblyCacheItem
helpviewer_keywords:
- IAssemblyCache::CreateAssemblyCacheItem method [.NET Framework fusion]
- CreateAssemblyCacheItem method [.NET Framework fusion]
ms.assetid: 017a7ba5-aaaf-44e2-9cbe-ceebef259df0
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 84291d3dea34aba43889baeb1f6e3d501f71b782
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="iassemblycachecreateassemblycacheitem-method"></a><span data-ttu-id="a8188-102">IAssemblyCache::CreateAssemblyCacheItem 方法</span><span class="sxs-lookup"><span data-stu-id="a8188-102">IAssemblyCache::CreateAssemblyCacheItem Method</span></span>
<span data-ttu-id="a8188-103">取得新的參考[IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)物件。</span><span class="sxs-lookup"><span data-stu-id="a8188-103">Gets a reference to a new [IAssemblyCacheItem](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8188-104">語法</span><span class="sxs-lookup"><span data-stu-id="a8188-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyCacheItem (  
    [in]  DWORD dwFlags,  
    [in]  PVOID pvReserved,  
    [out] IAssemblyCacheItem **ppAsmItem,  
    [in, optional] LPCWSTR pszAssemblyName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8188-105">參數</span><span class="sxs-lookup"><span data-stu-id="a8188-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="a8188-106">[in]支援下列值： 旗標。</span><span class="sxs-lookup"><span data-stu-id="a8188-106">[in] Flags defined in Fusion.idl.</span></span> <span data-ttu-id="a8188-107">支援下列值：</span><span class="sxs-lookup"><span data-stu-id="a8188-107">The following values are supported:</span></span>  
  
-   <span data-ttu-id="a8188-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0X00000001)</span><span class="sxs-lookup"><span data-stu-id="a8188-108">IASSEMBLYCACHE_INSTALL_FLAG_REFRESH (0x00000001)</span></span>  
  
-   <span data-ttu-id="a8188-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0X00000002)</span><span class="sxs-lookup"><span data-stu-id="a8188-109">IASSEMBLYCACHE_INSTALL_FLAG_FORCE_REFRESH (0x00000002)</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="a8188-110">[in]保留供未來擴充。</span><span class="sxs-lookup"><span data-stu-id="a8188-110">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="a8188-111">`pvReserved`必須是 null 參考。</span><span class="sxs-lookup"><span data-stu-id="a8188-111">`pvReserved` must be a null reference.</span></span>  
  
 `ppAsmItem`  
 <span data-ttu-id="a8188-112">[out]傳回`IAssemblyCacheItem`指標。</span><span class="sxs-lookup"><span data-stu-id="a8188-112">[out] The returned `IAssemblyCacheItem` pointer.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="a8188-113">[in，選用]Uncanonicalized、 以逗號分隔`name=value`組。</span><span class="sxs-lookup"><span data-stu-id="a8188-113">[in, optional] Uncanonicalized, comma-separated `name=value` pairs.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8188-114">需求</span><span class="sxs-lookup"><span data-stu-id="a8188-114">Requirements</span></span>  
 <span data-ttu-id="a8188-115">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8188-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8188-116">**標頭：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="a8188-116">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="a8188-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8188-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8188-118">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a8188-118">See Also</span></span>  
 [<span data-ttu-id="a8188-119">IAssemblyCache 介面</span><span class="sxs-lookup"><span data-stu-id="a8188-119">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [<span data-ttu-id="a8188-120">IAssemblyCacheItem 介面</span><span class="sxs-lookup"><span data-stu-id="a8188-120">IAssemblyCacheItem Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)