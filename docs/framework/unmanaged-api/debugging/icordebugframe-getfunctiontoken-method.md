---
title: "ICorDebugFrame::GetFunctionToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFrame.GetFunctionToken
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFrame::GetFunctionToken
helpviewer_keywords:
- ICorDebugFrame::GetFunctionToken method [.NET Framework debugging]
- GetFunctionToken method [.NET Framework debugging]
ms.assetid: a46925b3-3bf8-404f-9f30-a86ae41032c1
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d7a3e4300c32a32fd76f253d34581f53e4afd95e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugframegetfunctiontoken-method"></a><span data-ttu-id="664cb-102">ICorDebugFrame::GetFunctionToken 方法</span><span class="sxs-lookup"><span data-stu-id="664cb-102">ICorDebugFrame::GetFunctionToken Method</span></span>
<span data-ttu-id="664cb-103">取得包含此堆疊框架相關聯的程式碼的函式中繼資料語彙基元。</span><span class="sxs-lookup"><span data-stu-id="664cb-103">Gets the metadata token for the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="664cb-104">語法</span><span class="sxs-lookup"><span data-stu-id="664cb-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionToken (  
    [out] mdMethodDef        *pToken  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="664cb-105">參數</span><span class="sxs-lookup"><span data-stu-id="664cb-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="664cb-106">[out]指標`mdMethodDef`語彙基元所參考的函式的中繼資料。</span><span class="sxs-lookup"><span data-stu-id="664cb-106">[out] A pointer to an `mdMethodDef` token that references the metadata for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="664cb-107">需求</span><span class="sxs-lookup"><span data-stu-id="664cb-107">Requirements</span></span>  
 <span data-ttu-id="664cb-108">**平台：**看到[系統需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="664cb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="664cb-109">**標頭：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="664cb-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="664cb-110">**程式庫：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="664cb-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="664cb-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="664cb-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>