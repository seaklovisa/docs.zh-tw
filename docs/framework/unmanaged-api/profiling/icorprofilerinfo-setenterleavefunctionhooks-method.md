---
title: "ICorProfilerInfo::SetEnterLeaveFunctionHooks 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.SetEnterLeaveFunctionHooks
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::SetEnterLeaveFunctionHooks
helpviewer_keywords:
- SetEnterLeaveFunctionHooks method [.NET Framework profiling]
- ICorProfilerInfo::SetEnterLeaveFunctionHooks method [.NET Framework profiling]
ms.assetid: 72399636-c219-4ffd-8ac8-39432c9d4641
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c2bf897ce41e2d9a8b4c7b9eeb4053ea0e9ad951
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfosetenterleavefunctionhooks-method"></a><span data-ttu-id="e40ae-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks 方法</span><span class="sxs-lookup"><span data-stu-id="e40ae-102">ICorProfilerInfo::SetEnterLeaveFunctionHooks Method</span></span>
<span data-ttu-id="e40ae-103">指定程式碼剖析工具實作函式上 「 輸入 」、 「 保留 」 和 「 tailcall"攔截 managed 函式的呼叫。</span><span class="sxs-lookup"><span data-stu-id="e40ae-103">Specifies profiler-implemented functions to be called on "enter", "leave", and "tailcall" hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e40ae-104">語法</span><span class="sxs-lookup"><span data-stu-id="e40ae-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks(  
    [in] FunctionEnter    *pFuncEnter,  
    [in] FunctionLeave    *pFuncLeave,  
    [in] FunctionTailcall *pFuncTailcall);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e40ae-105">參數</span><span class="sxs-lookup"><span data-stu-id="e40ae-105">Parameters</span></span>  
 `pFuncEnter`  
 <span data-ttu-id="e40ae-106">[in]指向要做為實作[FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md)回呼。</span><span class="sxs-lookup"><span data-stu-id="e40ae-106">[in] A pointer to the implementation to be used as the [FunctionEnter](../../../../docs/framework/unmanaged-api/profiling/functionenter-function.md) callback.</span></span>  
  
 `pFuncLeave`  
 <span data-ttu-id="e40ae-107">[in]指向要做為實作[FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md)回呼。</span><span class="sxs-lookup"><span data-stu-id="e40ae-107">[in] A pointer to the implementation to be used as the [FunctionLeave](../../../../docs/framework/unmanaged-api/profiling/functionleave-function.md) callback.</span></span>  
  
 `pFuncTailcall`  
 <span data-ttu-id="e40ae-108">[in]指向要做為實作[FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md)回呼。</span><span class="sxs-lookup"><span data-stu-id="e40ae-108">[in] A pointer to the implementation to be used as the [FunctionTailcall](../../../../docs/framework/unmanaged-api/profiling/functiontailcall-function.md) callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e40ae-109">備註</span><span class="sxs-lookup"><span data-stu-id="e40ae-109">Remarks</span></span>  
 <span data-ttu-id="e40ae-110">在.NET Framework 1.0 版中，每個函式指標可以是 null 可停用該對應的回呼。</span><span class="sxs-lookup"><span data-stu-id="e40ae-110">In the .NET Framework version 1.0, each function pointer can be null to disable that corresponding callback.</span></span>  
  
 <span data-ttu-id="e40ae-111">只有一組回呼可以是作用中一次。</span><span class="sxs-lookup"><span data-stu-id="e40ae-111">Only one set of callbacks can be active at a time.</span></span> <span data-ttu-id="e40ae-112">因此，如果程式碼剖析工具呼叫兩者`SetEnterLeaveFunctionHooks`和[icorprofilerinfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)，然後`SetEnterLeaveFunctionHooks2`優先。</span><span class="sxs-lookup"><span data-stu-id="e40ae-112">Thus, if a profiler calls both `SetEnterLeaveFunctionHooks` and [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), then `SetEnterLeaveFunctionHooks2` takes precedence.</span></span>  
  
 <span data-ttu-id="e40ae-113">`SetEnterLeaveFunctionHooks`方法可以呼叫只會從程式碼剖析工具[icorprofilercallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)回呼。</span><span class="sxs-lookup"><span data-stu-id="e40ae-113">The `SetEnterLeaveFunctionHooks` method can be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e40ae-114">需求</span><span class="sxs-lookup"><span data-stu-id="e40ae-114">Requirements</span></span>  
 <span data-ttu-id="e40ae-115">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e40ae-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e40ae-116">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e40ae-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e40ae-117">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e40ae-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e40ae-118">**.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e40ae-118">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e40ae-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="e40ae-119">See Also</span></span>  
 [<span data-ttu-id="e40ae-120">ICorProfilerInfo 介面</span><span class="sxs-lookup"><span data-stu-id="e40ae-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)