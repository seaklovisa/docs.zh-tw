---
title: "ICorDebugRemoteTarget::GetHostName 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugRemoteTarget.GetHostName
api_location: CorDebug.dll
api_type: COM
f1_keywords: ICorDebugRemoteTarget::GetHostName
helpviewer_keywords:
- ICorDebugRemoteTarget::GetHostName method [.NET Framework debugging]
- GetHostName method, ICorDebugRemoteTarget interface [.NET Framework debugging]
ms.assetid: 1c7276f7-7e54-470c-808c-e13745ac07a1
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2af5d75145b9fdd2d370b76f798c5e350d8bec50
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugremotetargetgethostname-method"></a><span data-ttu-id="a8224-102">ICorDebugRemoteTarget::GetHostName 方法</span><span class="sxs-lookup"><span data-stu-id="a8224-102">ICorDebugRemoteTarget::GetHostName Method</span></span>
<span data-ttu-id="a8224-103">傳回遠端偵錯目標電腦的完整網域名稱或 IPv4 位址。</span><span class="sxs-lookup"><span data-stu-id="a8224-103">Returns the fully qualified domain name or IPv4 address of the remote debugging target machine.</span></span> <span data-ttu-id="a8224-104">目前不支援 IPV6。</span><span class="sxs-lookup"><span data-stu-id="a8224-104">IPV6 is not supported at this time.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a8224-105">語法</span><span class="sxs-lookup"><span data-stu-id="a8224-105">Syntax</span></span>  
  
```  
HRESULT GetHostName (  
    [in] ULONG32      cchHostName,  
    [out] ULONG32*    pcchHostName,  
    [out, size_is(cchHostName), length_is(*pcchHostName)]  
            WCHAR szHostName[]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a8224-106">參數</span><span class="sxs-lookup"><span data-stu-id="a8224-106">Parameters</span></span>  
 `cchHostName`  
 <span data-ttu-id="a8224-107">[in]大小，以字元為單位的`szHostName`緩衝區。</span><span class="sxs-lookup"><span data-stu-id="a8224-107">[in] The size, in characters, of the `szHostName` buffer.</span></span> <span data-ttu-id="a8224-108">如果這個參數是 0 (零)，則 `szHostName` 必須是 null。</span><span class="sxs-lookup"><span data-stu-id="a8224-108">If this parameter is 0 (zero), `szHostName` must be null.</span></span>  
  
 `pcchHostName`  
 <span data-ttu-id="a8224-109">[out] 在主機名稱或 IP 位址中的字元數，包括 null 結束字元。</span><span class="sxs-lookup"><span data-stu-id="a8224-109">[out] The number of characters, including a null terminator, in the host name or IP address.</span></span> <span data-ttu-id="a8224-110">此參數可以是 null。</span><span class="sxs-lookup"><span data-stu-id="a8224-110">This parameter can be null.</span></span>  
  
 `szHostName`  
 <span data-ttu-id="a8224-111">[out] 包含主機名稱或 IP 位址的緩衝區。</span><span class="sxs-lookup"><span data-stu-id="a8224-111">[out] Buffer that contains the host name or IP address.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a8224-112">傳回值</span><span class="sxs-lookup"><span data-stu-id="a8224-112">Return Value</span></span>  
 <span data-ttu-id="a8224-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a8224-113">S_OK</span></span>  
 <span data-ttu-id="a8224-114">成功傳回主機名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a8224-114">The host name or IP address was successfully returned.</span></span>  
  
 <span data-ttu-id="a8224-115">E_FAIL (或其他 E_ 傳回碼)</span><span class="sxs-lookup"><span data-stu-id="a8224-115">E_FAIL (or other E_ return codes)</span></span>  
 <span data-ttu-id="a8224-116">無法傳回主機名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="a8224-116">Unable to return the host name or IP address.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a8224-117">備註</span><span class="sxs-lookup"><span data-stu-id="a8224-117">Remarks</span></span>  
 <span data-ttu-id="a8224-118">這個方法是由偵錯工具寫入器實作。</span><span class="sxs-lookup"><span data-stu-id="a8224-118">This method is implemented by the debugger writer.</span></span> <span data-ttu-id="a8224-119">它必須遵守多項呼叫開發架構：第一次呼叫時，呼叫端會將 null 傳遞給 `cchHostName` 和 `szHostName`，而 `pcchHostName` 會傳回所需的緩衝區大小。</span><span class="sxs-lookup"><span data-stu-id="a8224-119">It must follow the multiple call paradigm: On the first call, the caller passes null to both `cchHostName` and `szHostName`, and `pcchHostName` returns the size of the required buffer .</span></span> <span data-ttu-id="a8224-120">第二次呼叫時，先前傳回的大小會在 `cchHostName` 中傳遞，而大小適當的緩衝區會在 `szHostName` 中傳遞。</span><span class="sxs-lookup"><span data-stu-id="a8224-120">On the second call, the size that was previously returned is passed in `cchHostName`, and an appropriately sized buffer is passed in `szHostName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a8224-121">需求</span><span class="sxs-lookup"><span data-stu-id="a8224-121">Requirements</span></span>  
 <span data-ttu-id="a8224-122">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a8224-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a8224-123">**標頭：** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="a8224-123">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="a8224-124">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8224-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a8224-125">**.NET framework 版本：** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="a8224-125">**.NET Framework Versions:** 3.5 SP1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8224-126">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a8224-126">See Also</span></span>  
 [<span data-ttu-id="a8224-127">ICorDebugRemoteTarget 介面</span><span class="sxs-lookup"><span data-stu-id="a8224-127">ICorDebugRemoteTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugremotetarget-interface.md)  
 [<span data-ttu-id="a8224-128">ICorDebug 介面</span><span class="sxs-lookup"><span data-stu-id="a8224-128">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)