---
title: "COR_PRF_STATIC_TYPE 列舉"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_STATIC_TYPE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_STATIC_TYPE
helpviewer_keywords: COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 446967cc157962a1ec4a87193bbf84b1a356efa6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="corprfstatictype-enumeration"></a><span data-ttu-id="7d702-102">COR_PRF_STATIC_TYPE 列舉</span><span class="sxs-lookup"><span data-stu-id="7d702-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="7d702-103">指出欄位是否為靜態，若是靜態，則欄位套用的是靜態品質。</span><span class="sxs-lookup"><span data-stu-id="7d702-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="7d702-104">這些值可以表示的欄位具有多個使用位元 OR 運算結合不同的靜態品質。</span><span class="sxs-lookup"><span data-stu-id="7d702-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7d702-105">語法</span><span class="sxs-lookup"><span data-stu-id="7d702-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="7d702-106">成員</span><span class="sxs-lookup"><span data-stu-id="7d702-106">Members</span></span>  
  
|<span data-ttu-id="7d702-107">成員</span><span class="sxs-lookup"><span data-stu-id="7d702-107">Member</span></span>|<span data-ttu-id="7d702-108">說明</span><span class="sxs-lookup"><span data-stu-id="7d702-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="7d702-109">欄位不是靜態的。</span><span class="sxs-lookup"><span data-stu-id="7d702-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="7d702-110">此欄位是應用程式定義域靜態。</span><span class="sxs-lookup"><span data-stu-id="7d702-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="7d702-111">此欄位是執行緒靜態。</span><span class="sxs-lookup"><span data-stu-id="7d702-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="7d702-112">此欄位是靜態內容。</span><span class="sxs-lookup"><span data-stu-id="7d702-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="7d702-113">此欄位是相對虛擬位址 (RVA) 為靜態。</span><span class="sxs-lookup"><span data-stu-id="7d702-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d702-114">需求</span><span class="sxs-lookup"><span data-stu-id="7d702-114">Requirements</span></span>  
 <span data-ttu-id="7d702-115">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7d702-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d702-116">**標頭：** CorProf.idl、CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7d702-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7d702-117">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7d702-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7d702-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d702-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d702-119">另請參閱</span><span class="sxs-lookup"><span data-stu-id="7d702-119">See Also</span></span>  
 [<span data-ttu-id="7d702-120">分析列舉</span><span class="sxs-lookup"><span data-stu-id="7d702-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)