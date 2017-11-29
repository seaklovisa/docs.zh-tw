---
title: "ICorProfilerInfo3::GetStringLayout2 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetStringLayout2 Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetStringLayout2
helpviewer_keywords:
- ICorProfilerInfo3::GetStringLayout2 method [.NET Framework profiling]
- GetStringLayout2 method [.NET Framework profiling]
ms.assetid: 1a268496-ee51-4d84-8700-ee56fd0c499d
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: de89776c6208ec7e3434fa747057edbf818ec013
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getstringlayout2-method"></a><span data-ttu-id="a1272-102">ICorProfilerInfo3::GetStringLayout2 方法</span><span class="sxs-lookup"><span data-stu-id="a1272-102">ICorProfilerInfo3::GetStringLayout2 Method</span></span>
<span data-ttu-id="a1272-103">取得字串物件配置的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a1272-103">Gets information about the layout of a string object.</span></span> <span data-ttu-id="a1272-104">這個方法會取代[icorprofilerinfo2:: Getstringlayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a1272-104">This method supersedes the [ICorProfilerInfo2::GetStringLayout](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a1272-105">語法</span><span class="sxs-lookup"><span data-stu-id="a1272-105">Syntax</span></span>  
  
```  
HRESULT GetStringLayout2(  
    [out] ULONG *pStringLengthOffset,  
    [out] ULONG *pBufferOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a1272-106">參數</span><span class="sxs-lookup"><span data-stu-id="a1272-106">Parameters</span></span>  
 `pStringLengthOffset`  
 <span data-ttu-id="a1272-107">[out]指標的位置，相對於位移`ObjectID`儲存字串本身長度的指標。</span><span class="sxs-lookup"><span data-stu-id="a1272-107">[out] A pointer to the offset of the location, relative to the `ObjectID` pointer, that stores the length of the string itself.</span></span> <span data-ttu-id="a1272-108">長度會儲存為`DWORD`。</span><span class="sxs-lookup"><span data-stu-id="a1272-108">The length is stored as a `DWORD`.</span></span>  
  
 `pBufferOffset`  
 <span data-ttu-id="a1272-109">[out]相對於的緩衝區位移的指標`ObjectID`指標，其中儲存的寬字元字串。</span><span class="sxs-lookup"><span data-stu-id="a1272-109">[out] A pointer to the offset of the buffer, relative to the `ObjectID` pointer, which stores the string of wide characters.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a1272-110">備註</span><span class="sxs-lookup"><span data-stu-id="a1272-110">Remarks</span></span>  
 <span data-ttu-id="a1272-111">字串可能會或可能不是以 null 結尾。</span><span class="sxs-lookup"><span data-stu-id="a1272-111">Strings may or may not be null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a1272-112">需求</span><span class="sxs-lookup"><span data-stu-id="a1272-112">Requirements</span></span>  
 <span data-ttu-id="a1272-113">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a1272-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a1272-114">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a1272-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a1272-115">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a1272-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a1272-116">**.NET framework 版本：**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a1272-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1272-117">另請參閱</span><span class="sxs-lookup"><span data-stu-id="a1272-117">See Also</span></span>  
 [<span data-ttu-id="a1272-118">ICorProfilerInfo3 介面</span><span class="sxs-lookup"><span data-stu-id="a1272-118">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="a1272-119">分析介面</span><span class="sxs-lookup"><span data-stu-id="a1272-119">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)