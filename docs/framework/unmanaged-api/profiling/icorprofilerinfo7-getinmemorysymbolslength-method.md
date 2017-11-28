---
title: "Icorprofilerinfo7:: Getinmemorysymbolslength 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type: COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34da00bdc33a836e5f459e6e4314f252e1e39e9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="a2518-102">Icorprofilerinfo7:: Getinmemorysymbolslength 方法</span><span class="sxs-lookup"><span data-stu-id="a2518-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="a2518-103">[在 .NET Framework 4.6.1 及更新版本中支援]</span><span class="sxs-lookup"><span data-stu-id="a2518-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="a2518-104">傳回的記憶體中的符號資料流的長度。</span><span class="sxs-lookup"><span data-stu-id="a2518-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a2518-105">語法</span><span class="sxs-lookup"><span data-stu-id="a2518-105">Syntax</span></span>  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a2518-106">參數</span><span class="sxs-lookup"><span data-stu-id="a2518-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="a2518-107">[in]包含記憶體中資料流之模組的識別碼。</span><span class="sxs-lookup"><span data-stu-id="a2518-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="a2518-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="a2518-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="a2518-109">[out]指標`DWORD`值，這個方法傳回時，包含以位元組為單位的資料流的長度值。</span><span class="sxs-lookup"><span data-stu-id="a2518-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a2518-110">傳回值</span><span class="sxs-lookup"><span data-stu-id="a2518-110">Return Value</span></span>  
 <span data-ttu-id="a2518-111">方法會傳回`S_OK`如果記憶體資料流的長度可以判斷，即使它是零 (0)。</span><span class="sxs-lookup"><span data-stu-id="a2518-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="a2518-112">方法會傳回`CORPROF_E_MODULE_IS_DYNAMIC`如果方法使用建立<xref:System.Reflection.Emit?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="a2518-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a2518-113">備註</span><span class="sxs-lookup"><span data-stu-id="a2518-113">Remarks</span></span>  
 <span data-ttu-id="a2518-114">如果模組有記憶體中的符號，資料流的長度會置於`pCountSymbolBytes`。</span><span class="sxs-lookup"><span data-stu-id="a2518-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="a2518-115">如果模組沒有記憶體中的符號， `*pCountSymbolBytes = 0`。</span><span class="sxs-lookup"><span data-stu-id="a2518-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a2518-116">目前的實作不支援這些事件處理常式。</span><span class="sxs-lookup"><span data-stu-id="a2518-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="a2518-117">如果使用 Reflection.Emit 建立模組，則方法會傳回`CORPROF_E_MODULE_IS_DYNAMIC`。</span><span class="sxs-lookup"><span data-stu-id="a2518-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a2518-118">需求</span><span class="sxs-lookup"><span data-stu-id="a2518-118">Requirements</span></span>  
 <span data-ttu-id="a2518-119">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2518-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2518-120">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a2518-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a2518-121">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a2518-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a2518-122">**.NET framework 版本：**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2518-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2518-123">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a2518-123">See Also</span></span>  
 [<span data-ttu-id="a2518-124">ICorProfilerInfo7 介面</span><span class="sxs-lookup"><span data-stu-id="a2518-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)