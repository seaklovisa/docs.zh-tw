---
title: "ICorDebug::Initialize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.Initialize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12665472b201e6d89be9c5cc6c78b82de067d6a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="8fd62-102">ICorDebug::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="8fd62-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="8fd62-103">初始化 `ICorDebug` 物件。</span><span class="sxs-lookup"><span data-stu-id="8fd62-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fd62-104">語法</span><span class="sxs-lookup"><span data-stu-id="8fd62-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8fd62-105">備註</span><span class="sxs-lookup"><span data-stu-id="8fd62-105">Remarks</span></span>  
 <span data-ttu-id="8fd62-106">偵錯工具必須呼叫`Initialize`在建立服務的時間來初始化偵錯。</span><span class="sxs-lookup"><span data-stu-id="8fd62-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="8fd62-107">必須在任何其他方法之前呼叫此方法`ICorDebug`呼叫。</span><span class="sxs-lookup"><span data-stu-id="8fd62-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fd62-108">需求</span><span class="sxs-lookup"><span data-stu-id="8fd62-108">Requirements</span></span>  
 <span data-ttu-id="8fd62-109">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8fd62-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8fd62-110">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8fd62-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8fd62-111">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8fd62-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8fd62-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8fd62-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fd62-113">另請參閱</span><span class="sxs-lookup"><span data-stu-id="8fd62-113">See Also</span></span>  
 [<span data-ttu-id="8fd62-114">ICorDebug 介面</span><span class="sxs-lookup"><span data-stu-id="8fd62-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)