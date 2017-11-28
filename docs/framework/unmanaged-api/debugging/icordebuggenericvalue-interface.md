---
title: ICorDebugGenericValue Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugGenericValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugGenericValue
helpviewer_keywords: ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61c159e30efb33dca4043e5b5306c9544acd614a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuggenericvalue-interface1"></a><span data-ttu-id="d583a-102">ICorDebugGenericValue Interface1</span><span class="sxs-lookup"><span data-stu-id="d583a-102">ICorDebugGenericValue Interface1</span></span>
<span data-ttu-id="d583a-103">「 ICorDebugValue"套用至所有值的子類別。</span><span class="sxs-lookup"><span data-stu-id="d583a-103">A subclass of "ICorDebugValue" that applies to all values.</span></span> <span data-ttu-id="d583a-104">這個介面提供值的 Get 和 Set 方法。</span><span class="sxs-lookup"><span data-stu-id="d583a-104">This interface provides Get and Set methods for the value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d583a-105">方法</span><span class="sxs-lookup"><span data-stu-id="d583a-105">Methods</span></span>  
  
|<span data-ttu-id="d583a-106">方法</span><span class="sxs-lookup"><span data-stu-id="d583a-106">Method</span></span>|<span data-ttu-id="d583a-107">說明</span><span class="sxs-lookup"><span data-stu-id="d583a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d583a-108">GetValue 方法</span><span class="sxs-lookup"><span data-stu-id="d583a-108">GetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|<span data-ttu-id="d583a-109">將值複製到指定的緩衝區。</span><span class="sxs-lookup"><span data-stu-id="d583a-109">Copies the value into the specified buffer.</span></span>|  
|[<span data-ttu-id="d583a-110">SetValue 方法</span><span class="sxs-lookup"><span data-stu-id="d583a-110">SetValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|<span data-ttu-id="d583a-111">從指定的緩衝區複製的新值。</span><span class="sxs-lookup"><span data-stu-id="d583a-111">Copies a new value from the specified buffer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d583a-112">備註</span><span class="sxs-lookup"><span data-stu-id="d583a-112">Remarks</span></span>  
 <span data-ttu-id="d583a-113">`ICorDebugGenericValue`因為它是不可遠端是子介面。</span><span class="sxs-lookup"><span data-stu-id="d583a-113">`ICorDebugGenericValue` is a sub-interface because it is non-remotable.</span></span>  
  
 <span data-ttu-id="d583a-114">對於參考型別，這個值會是參考，而不是參考的內容。</span><span class="sxs-lookup"><span data-stu-id="d583a-114">For reference types, the value is the reference rather than the contents of the reference.</span></span>  
  
 <span data-ttu-id="d583a-115">這個介面不支援跨電腦或跨處理序的遠端呼叫。</span><span class="sxs-lookup"><span data-stu-id="d583a-115">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d583a-116">這個介面不支援跨電腦或跨處理序的遠端呼叫。</span><span class="sxs-lookup"><span data-stu-id="d583a-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d583a-117">需求</span><span class="sxs-lookup"><span data-stu-id="d583a-117">Requirements</span></span>  
 <span data-ttu-id="d583a-118">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d583a-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d583a-119">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d583a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d583a-120">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d583a-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d583a-121">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d583a-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d583a-122">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d583a-122">See Also</span></span>  
    
 [<span data-ttu-id="d583a-123">偵錯介面</span><span class="sxs-lookup"><span data-stu-id="d583a-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)