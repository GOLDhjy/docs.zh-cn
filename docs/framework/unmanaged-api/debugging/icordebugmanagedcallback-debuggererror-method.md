---
title: "ICorDebugManagedCallback::DebuggerError 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.DebuggerError
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::DebuggerError
helpviewer_keywords:
- DebuggerError method [.NET Framework debugging]
- ICorDebugManagedCallback::DebuggerError method [.NET Framework debugging]
ms.assetid: 9e983d11-eaf3-4741-b936-29ec456384a3
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c4eb16762d2a0db01c3cc921712a89995e0c87c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmanagedcallbackdebuggererror-method"></a><span data-ttu-id="08aa5-102">ICorDebugManagedCallback::DebuggerError 方法</span><span class="sxs-lookup"><span data-stu-id="08aa5-102">ICorDebugManagedCallback::DebuggerError Method</span></span>
<span data-ttu-id="08aa5-103">通知调试器，在尝试处理来自公共语言运行时 (CLR) 的事件时发生错误。</span><span class="sxs-lookup"><span data-stu-id="08aa5-103">Notifies the debugger that an error has occurred while attempting to handle an event from the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08aa5-104">语法</span><span class="sxs-lookup"><span data-stu-id="08aa5-104">Syntax</span></span>  
  
```  
HRESULT DebuggerError (  
    [in] ICorDebugProcess *pProcess,  
    [in] HRESULT           errorHR,  
    [in] DWORD             errorCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="08aa5-105">参数</span><span class="sxs-lookup"><span data-stu-id="08aa5-105">Parameters</span></span>  
 `pProcess`  
 <span data-ttu-id="08aa5-106">[in]指向一个表示发生该事件的过程的"ICorDebugProcess"对象的指针。</span><span class="sxs-lookup"><span data-stu-id="08aa5-106">[in] A pointer to an "ICorDebugProcess" object that represents the process in which the event occurred.</span></span>  
  
 `errorHR`  
 <span data-ttu-id="08aa5-107">[in]从事件处理程序返回了 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="08aa5-107">[in] The HRESULT value that was returned from the event handler.</span></span>  
  
 `errorCode`  
 <span data-ttu-id="08aa5-108">[in]一个整数，指定 CLR 错误。</span><span class="sxs-lookup"><span data-stu-id="08aa5-108">[in] An integer that specifies the CLR error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="08aa5-109">备注</span><span class="sxs-lookup"><span data-stu-id="08aa5-109">Remarks</span></span>  
 <span data-ttu-id="08aa5-110">该过程可能被放入传递模式，具体取决于错误的性质。</span><span class="sxs-lookup"><span data-stu-id="08aa5-110">The process may be placed into pass-through mode, depending on the nature of the error.</span></span>  
  
 <span data-ttu-id="08aa5-111">`DebugError`回调指示，调试服务已被禁用由于错误，因此调试器应提供错误消息给用户。</span><span class="sxs-lookup"><span data-stu-id="08aa5-111">The `DebugError` callback indicates that debugging services have been disabled due to an error, so debuggers should make the error message available to the user.</span></span> <span data-ttu-id="08aa5-112">[Icordebugprocess:: Getid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)将安全地调用，但所有其他方法，包括[icordebug:: Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md)，不应该调用。</span><span class="sxs-lookup"><span data-stu-id="08aa5-112">[ICorDebugProcess::GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md) will be safe to call, but all other methods, including [ICorDebug::Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebug-terminate-method.md), should not be called.</span></span> <span data-ttu-id="08aa5-113">调试器应使用操作系统工具来终止进程。</span><span class="sxs-lookup"><span data-stu-id="08aa5-113">The debugger should use operating-system facilities for terminating processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="08aa5-114">要求</span><span class="sxs-lookup"><span data-stu-id="08aa5-114">Requirements</span></span>  
 <span data-ttu-id="08aa5-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08aa5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08aa5-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="08aa5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="08aa5-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="08aa5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="08aa5-118">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08aa5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08aa5-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08aa5-119">See Also</span></span>  
 [<span data-ttu-id="08aa5-120">ICorDebugManagedCallback 接口</span><span class="sxs-lookup"><span data-stu-id="08aa5-120">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)