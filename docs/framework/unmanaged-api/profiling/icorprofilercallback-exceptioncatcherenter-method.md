---
title: "ICorProfilerCallback::ExceptionCatcherEnter 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionCatcherEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b1605fdca3f5aa13ce4e29c0ff2fb42383512e6e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="6918d-102">ICorProfilerCallback::ExceptionCatcherEnter 方法</span><span class="sxs-lookup"><span data-stu-id="6918d-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="6918d-103">通知控制項已傳遞至適當的程式碼剖析工具`catch`區塊。</span><span class="sxs-lookup"><span data-stu-id="6918d-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6918d-104">語法</span><span class="sxs-lookup"><span data-stu-id="6918d-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6918d-105">參數</span><span class="sxs-lookup"><span data-stu-id="6918d-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="6918d-106">[in]函式包含的識別項`catch`區塊。</span><span class="sxs-lookup"><span data-stu-id="6918d-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="6918d-107">[in]正在處理的例外狀況的識別項。</span><span class="sxs-lookup"><span data-stu-id="6918d-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6918d-108">備註</span><span class="sxs-lookup"><span data-stu-id="6918d-108">Remarks</span></span>  
 <span data-ttu-id="6918d-109">`ExceptionCatcherEnter`只有 catch 點是以在 just-in-time (JIT) 編譯器編譯程式碼呼叫方法。</span><span class="sxs-lookup"><span data-stu-id="6918d-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="6918d-110">在 unmanaged 程式碼或內部的程式碼的執行階段中不會攔截到例外狀況不會呼叫這項通知。</span><span class="sxs-lookup"><span data-stu-id="6918d-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="6918d-111">`objectId`值會傳遞一次回收無法移動的物件，因為由於`ExceptionThrown`通知。</span><span class="sxs-lookup"><span data-stu-id="6918d-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="6918d-112">因為堆疊可能不是處於允許記憶體回收，分析工具不應該在這個方法實作封鎖，因此無法啟用先佔式記憶體回收。</span><span class="sxs-lookup"><span data-stu-id="6918d-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="6918d-113">如果分析工具會封鎖這裡並嘗試執行記憶體回收、 執行階段將會封鎖此回呼傳回之前。</span><span class="sxs-lookup"><span data-stu-id="6918d-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="6918d-114">Managed 程式碼或任何方式原因 managed 記憶體配置中，不應該呼叫這個方法的程式碼剖析工具實作。</span><span class="sxs-lookup"><span data-stu-id="6918d-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6918d-115">需求</span><span class="sxs-lookup"><span data-stu-id="6918d-115">Requirements</span></span>  
 <span data-ttu-id="6918d-116">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6918d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6918d-117">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6918d-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6918d-118">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6918d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6918d-119">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6918d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6918d-120">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6918d-120">See Also</span></span>  
 [<span data-ttu-id="6918d-121">ICorProfilerCallback 介面</span><span class="sxs-lookup"><span data-stu-id="6918d-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="6918d-122">ExceptionCatcherLeave 方法</span><span class="sxs-lookup"><span data-stu-id="6918d-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)