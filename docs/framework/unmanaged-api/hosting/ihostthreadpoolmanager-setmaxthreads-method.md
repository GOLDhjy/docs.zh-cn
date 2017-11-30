---
title: "IHostThreadPoolManager::SetMaxThreads 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager.SetMaxThreads
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 69465029deb1db191c28313fb9a260d3c5ba5289
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a><span data-ttu-id="e3b31-102">IHostThreadPoolManager::SetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="e3b31-102">IHostThreadPoolManager::SetMaxThreads Method</span></span>
<span data-ttu-id="e3b31-103">设置最大主机可以维护在线程池中的线程数。</span><span class="sxs-lookup"><span data-stu-id="e3b31-103">Sets the maximum number of threads that the host can maintain in the thread pool.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3b31-104">语法</span><span class="sxs-lookup"><span data-stu-id="e3b31-104">Syntax</span></span>  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e3b31-105">参数</span><span class="sxs-lookup"><span data-stu-id="e3b31-105">Parameters</span></span>  
 `MaxThreads`  
 <span data-ttu-id="e3b31-106">线程池中辅助线程的最大数目。</span><span class="sxs-lookup"><span data-stu-id="e3b31-106">The maximum number of worker threads in the thread pool.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3b31-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e3b31-107">Return Value</span></span>  
  
|<span data-ttu-id="e3b31-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3b31-108">HRESULT</span></span>|<span data-ttu-id="e3b31-109">描述</span><span class="sxs-lookup"><span data-stu-id="e3b31-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3b31-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3b31-110">S_OK</span></span>|<span data-ttu-id="e3b31-111">`SetMaxThreads`已成功返回。</span><span class="sxs-lookup"><span data-stu-id="e3b31-111">`SetMaxThreads` returned successfully.</span></span>|  
|<span data-ttu-id="e3b31-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e3b31-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e3b31-113">公共语言运行时 (CLR) 尚未加载到进程中，或 CLR 处于不能运行托管的代码或成功处理调用的状态。</span><span class="sxs-lookup"><span data-stu-id="e3b31-113">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e3b31-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e3b31-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e3b31-115">调用操作已超时。</span><span class="sxs-lookup"><span data-stu-id="e3b31-115">The call timed out.</span></span>|  
|<span data-ttu-id="e3b31-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e3b31-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e3b31-117">调用方不拥有该锁。</span><span class="sxs-lookup"><span data-stu-id="e3b31-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e3b31-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e3b31-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e3b31-119">事件已被取消时被阻塞的线程，或者纤程正在等待它。</span><span class="sxs-lookup"><span data-stu-id="e3b31-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e3b31-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e3b31-120">E_FAIL</span></span>|<span data-ttu-id="e3b31-121">发生了未知的灾难性故障。</span><span class="sxs-lookup"><span data-stu-id="e3b31-121">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e3b31-122">如果某方法返回 E_FAIL，CLR 不再可用进程内。</span><span class="sxs-lookup"><span data-stu-id="e3b31-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e3b31-123">到托管方法的后续调用会返回 HOST_E_CLRNOTAVAILABLE。</span><span class="sxs-lookup"><span data-stu-id="e3b31-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e3b31-124">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="e3b31-124">E_NOTIMPL</span></span>|<span data-ttu-id="e3b31-125">主机未提供的实现`SetMaxThreads`。</span><span class="sxs-lookup"><span data-stu-id="e3b31-125">The host does not provide an implementation of `SetMaxThreads`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e3b31-126">备注</span><span class="sxs-lookup"><span data-stu-id="e3b31-126">Remarks</span></span>  
 <span data-ttu-id="e3b31-127">主机不需要以允许 CLR 进行配置的线程池大小。</span><span class="sxs-lookup"><span data-stu-id="e3b31-127">A host is not required to allow the CLR to configure the size of the thread pool.</span></span> <span data-ttu-id="e3b31-128">某些主机的如实现、 性能或可伸缩性的原因，可能需要对线程池的独有控制。</span><span class="sxs-lookup"><span data-stu-id="e3b31-128">Some hosts might want exclusive control over the thread pool, for reasons such as implementation, performance, or scalability.</span></span> <span data-ttu-id="e3b31-129">在这种情况下，主机应返回 E_NOTIMPL 的 HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="e3b31-129">In this case, a host should return an HRESULT value of E_NOTIMPL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3b31-130">要求</span><span class="sxs-lookup"><span data-stu-id="e3b31-130">Requirements</span></span>  
 <span data-ttu-id="e3b31-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e3b31-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3b31-132">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e3b31-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3b31-133">**库：**作为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e3b31-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3b31-134">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3b31-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3b31-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e3b31-135">See Also</span></span>  
 <xref:System.Threading.ThreadPool.SetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [<span data-ttu-id="e3b31-136">GetMaxThreads 方法</span><span class="sxs-lookup"><span data-stu-id="e3b31-136">GetMaxThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [<span data-ttu-id="e3b31-137">SetMinThreads 方法</span><span class="sxs-lookup"><span data-stu-id="e3b31-137">SetMinThreads Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [<span data-ttu-id="e3b31-138">IHostThreadPoolManager 接口</span><span class="sxs-lookup"><span data-stu-id="e3b31-138">IHostThreadPoolManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)