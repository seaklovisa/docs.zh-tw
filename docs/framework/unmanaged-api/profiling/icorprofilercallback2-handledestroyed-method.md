---
title: "ICorProfilerCallback2::HandleDestroyed 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.HandleDestroyed
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b661988b29e8c7d98ab23e049aa289f355ed543
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="d58a1-102">ICorProfilerCallback2::HandleDestroyed 方法</span><span class="sxs-lookup"><span data-stu-id="d58a1-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="d58a1-103">通知記憶體回收控制代碼已終結的程式碼分析工具。</span><span class="sxs-lookup"><span data-stu-id="d58a1-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d58a1-104">語法</span><span class="sxs-lookup"><span data-stu-id="d58a1-104">Syntax</span></span>  
  
```  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d58a1-105">參數</span><span class="sxs-lookup"><span data-stu-id="d58a1-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="d58a1-106">[in]記憶體回收控制代碼的識別碼。</span><span class="sxs-lookup"><span data-stu-id="d58a1-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d58a1-107">需求</span><span class="sxs-lookup"><span data-stu-id="d58a1-107">Requirements</span></span>  
 <span data-ttu-id="d58a1-108">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d58a1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d58a1-109">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d58a1-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d58a1-110">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d58a1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d58a1-111">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d58a1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d58a1-112">另請參閱</span><span class="sxs-lookup"><span data-stu-id="d58a1-112">See Also</span></span>  
 [<span data-ttu-id="d58a1-113">ICorProfilerCallback 介面</span><span class="sxs-lookup"><span data-stu-id="d58a1-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="d58a1-114">ICorProfilerCallback2 介面</span><span class="sxs-lookup"><span data-stu-id="d58a1-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)