---
title: "ICLRDataTarget2::AllocVirtual 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDataTarget2.AllocVirtual
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICLRDataTarget2::AllocVirtual
helpviewer_keywords:
- ICLRDataTarget2::AllocVirtual method [.NET Framework debugging]
- AllocVirtual method [.NET Framework debugging]
ms.assetid: e3226230-964b-47fb-9f53-d6fdbeda1e9e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e61b27ae7dcda8cc5e14d9c0f72f74c8bda13169
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget2allocvirtual-method"></a><span data-ttu-id="de782-102">ICLRDataTarget2::AllocVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="de782-102">ICLRDataTarget2::AllocVirtual Method</span></span>
<span data-ttu-id="de782-103">呼叫由 common language runtime (CLR) 資料存取服務此目標處理序的位址空間中配置記憶體。</span><span class="sxs-lookup"><span data-stu-id="de782-103">Called by the common language runtime (CLR) data access services to allocate memory in the address space of this target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de782-104">語法</span><span class="sxs-lookup"><span data-stu-id="de782-104">Syntax</span></span>  
  
```  
HRESULT AllocVirtual(  
    [in] CLRDATA_ADDRESS addr,  
    [in] ULONG32 size,  
    [in] ULONG32 typeFlags,  
    [in] ULONG32 protectFlags,  
    [out] CLRDATA_ADDRESS* virt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de782-105">參數</span><span class="sxs-lookup"><span data-stu-id="de782-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="de782-106">[in]A`CLRDATA_ADDRESS`值，指定所要求的起始位址配置的記憶體。</span><span class="sxs-lookup"><span data-stu-id="de782-106">[in] A `CLRDATA_ADDRESS` value that specifies the requested starting address of the memory to be allocated.</span></span>  
  
 `size`  
 <span data-ttu-id="de782-107">[in]以位元組為單位配置的記憶體大小。</span><span class="sxs-lookup"><span data-stu-id="de782-107">[in] The size, in bytes, of the memory to be allocated.</span></span>  
  
 `typeFlags`  
 <span data-ttu-id="de782-108">[in]控制記憶體配置的旗標。</span><span class="sxs-lookup"><span data-stu-id="de782-108">[in] Flags that control the allocation of memory.</span></span> <span data-ttu-id="de782-109">請參閱 Win32`VirtualAlloc`函式。</span><span class="sxs-lookup"><span data-stu-id="de782-109">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `protectFlags`  
 <span data-ttu-id="de782-110">[in]配置的記憶體保護屬性。</span><span class="sxs-lookup"><span data-stu-id="de782-110">[in] The protection attributes for the allocated memory.</span></span> <span data-ttu-id="de782-111">請參閱 Win32`VirtualAlloc`函式。</span><span class="sxs-lookup"><span data-stu-id="de782-111">See the Win32 `VirtualAlloc` function.</span></span>  
  
 `virt`  
 <span data-ttu-id="de782-112">[out]指標`CLRDATA_ADDRESS`值，指定配置的記憶體的實際開始位址。</span><span class="sxs-lookup"><span data-stu-id="de782-112">[out] A pointer to a `CLRDATA_ADDRESS` value that specifies the actual starting address of the allocated memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de782-113">備註</span><span class="sxs-lookup"><span data-stu-id="de782-113">Remarks</span></span>  
 <span data-ttu-id="de782-114">`AllocVirtual`方法做為 Win32 的邏輯包裝函數`VirtualAlloc`函式。</span><span class="sxs-lookup"><span data-stu-id="de782-114">The `AllocVirtual` method serves as a logical wrapper for the Win32 `VirtualAlloc` function.</span></span>  
  
 <span data-ttu-id="de782-115">此方法是由偵錯應用程式的作者來實作。</span><span class="sxs-lookup"><span data-stu-id="de782-115">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de782-116">需求</span><span class="sxs-lookup"><span data-stu-id="de782-116">Requirements</span></span>  
 <span data-ttu-id="de782-117">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de782-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de782-118">**標頭：** ClrData.idl、 ClrData.h</span><span class="sxs-lookup"><span data-stu-id="de782-118">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="de782-119">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de782-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="de782-120">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de782-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de782-121">另請參閱</span><span class="sxs-lookup"><span data-stu-id="de782-121">See Also</span></span>  
 [<span data-ttu-id="de782-122">ICLRDataTarget2 介面</span><span class="sxs-lookup"><span data-stu-id="de782-122">ICLRDataTarget2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-interface.md)  
 [<span data-ttu-id="de782-123">FreeVirtual 方法</span><span class="sxs-lookup"><span data-stu-id="de782-123">FreeVirtual Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget2-freevirtual-method.md)