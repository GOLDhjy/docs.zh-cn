---
title: "ICLRRuntimeHost::GetCLRControl 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeHost.GetCLRControl
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeHost::GetCLRControl
helpviewer_keywords:
- ICLRRuntimeHost::GetCLRControl method [.NET Framework hosting]
- GetCLRControl method [.NET Framework hosting]
ms.assetid: e47e3655-efd5-4572-a1dc-50c69bf2a468
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4072c21ea002523fe8086151a40c4e17b775ebbb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimehostgetclrcontrol-method"></a><span data-ttu-id="13c7c-102">ICLRRuntimeHost::GetCLRControl 方法</span><span class="sxs-lookup"><span data-stu-id="13c7c-102">ICLRRuntimeHost::GetCLRControl Method</span></span>
<span data-ttu-id="13c7c-103">获取类型的接口指针[ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)主机可用于自定义的公共语言运行时 (CLR) 方面。</span><span class="sxs-lookup"><span data-stu-id="13c7c-103">Gets an interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that hosts can use to customize aspects of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13c7c-104">语法</span><span class="sxs-lookup"><span data-stu-id="13c7c-104">Syntax</span></span>  
  
```  
HRESULT GetCLRControl(  
    [out] ICLRControl** pCLRControl  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="13c7c-105">参数</span><span class="sxs-lookup"><span data-stu-id="13c7c-105">Parameters</span></span>  
 `pCLRControl`  
 <span data-ttu-id="13c7c-106">[out]类型的接口指针[ICLRControl 接口](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)，使主机可以配置的 CLR 的其他方面。</span><span class="sxs-lookup"><span data-stu-id="13c7c-106">[out] An interface pointer of type [ICLRControl Interface](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md) that enables hosts to configure additional aspects of the CLR.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13c7c-107">返回值</span><span class="sxs-lookup"><span data-stu-id="13c7c-107">Return Value</span></span>  
  
|<span data-ttu-id="13c7c-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="13c7c-108">HRESULT</span></span>|<span data-ttu-id="13c7c-109">描述</span><span class="sxs-lookup"><span data-stu-id="13c7c-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="13c7c-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="13c7c-110">S_OK</span></span>|<span data-ttu-id="13c7c-111">`GetCLRControl`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="13c7c-111">`GetCLRControl` returned successfully.</span></span>|  
|<span data-ttu-id="13c7c-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="13c7c-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="13c7c-113">CLR 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="13c7c-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="13c7c-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="13c7c-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="13c7c-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="13c7c-115">The call timed out.</span></span>|  
|<span data-ttu-id="13c7c-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="13c7c-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="13c7c-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="13c7c-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="13c7c-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="13c7c-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="13c7c-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="13c7c-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="13c7c-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="13c7c-120">E_FAIL</span></span>|<span data-ttu-id="13c7c-121">出现未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="13c7c-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="13c7c-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="13c7c-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="13c7c-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="13c7c-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="13c7c-124">HOST_E_INVALIDOPERATION</span><span class="sxs-lookup"><span data-stu-id="13c7c-124">HOST_E_INVALIDOPERATION</span></span>|<span data-ttu-id="13c7c-125">已经启动了 CLR。</span><span class="sxs-lookup"><span data-stu-id="13c7c-125">The CLR has already started.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="13c7c-126">备注</span><span class="sxs-lookup"><span data-stu-id="13c7c-126">Remarks</span></span>  
 <span data-ttu-id="13c7c-127">`ICLRControl`提供[GetCLRManager 方法](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md)方法，使主机可用于访问管理器类型的接口指针。</span><span class="sxs-lookup"><span data-stu-id="13c7c-127">`ICLRControl` provides the [GetCLRManager Method](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method, which enables the host to get an interface pointer to one of the manager types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13c7c-128">要求</span><span class="sxs-lookup"><span data-stu-id="13c7c-128">Requirements</span></span>  
 <span data-ttu-id="13c7c-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13c7c-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13c7c-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="13c7c-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13c7c-131">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="13c7c-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13c7c-132">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13c7c-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13c7c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13c7c-133">See Also</span></span>  
 [<span data-ttu-id="13c7c-134">ICLRControl 接口</span><span class="sxs-lookup"><span data-stu-id="13c7c-134">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="13c7c-135">ICLRRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="13c7c-135">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)