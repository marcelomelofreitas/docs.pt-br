---
title: Interface IGCHost
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost
helpviewer_keywords: IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0f398c09569a855291a1565ce63b513161a803
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="igchost-interface"></a><span data-ttu-id="57938-102">Interface IGCHost</span><span class="sxs-lookup"><span data-stu-id="57938-102">IGCHost Interface</span></span>
<span data-ttu-id="57938-103">Fornece métodos para obter informações sobre o sistema de coleta de lixo e para controlar alguns aspectos da coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="57938-103">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57938-104">Começando com o [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], você pode usar o [Igchost2](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) método para definir o tamanho de um segmento de coleta de lixo e o tamanho máximo da geração do sistema de coleta de lixo 0 como valores maiores que o `DWORD` limite imposto pelo [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="57938-104">Starting with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], you can use the [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) method to set the size of a garbage collection segment and the maximum size of the garbage collection system's generation 0 to values greater than the `DWORD` limit that is imposed by the [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="57938-105">Esta interface é somente ao uso especializado.</span><span class="sxs-lookup"><span data-stu-id="57938-105">This interface is for expert usage only.</span></span> <span data-ttu-id="57938-106">Se usado incorretamente, isso poderá afetar o desempenho de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="57938-106">It can affect the performance of an application if used improperly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="57938-107">Métodos</span><span class="sxs-lookup"><span data-stu-id="57938-107">Methods</span></span>  
  
|<span data-ttu-id="57938-108">Método</span><span class="sxs-lookup"><span data-stu-id="57938-108">Method</span></span>|<span data-ttu-id="57938-109">Descrição</span><span class="sxs-lookup"><span data-stu-id="57938-109">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="57938-110">Método Collect</span><span class="sxs-lookup"><span data-stu-id="57938-110">Collect Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|<span data-ttu-id="57938-111">Força uma coleta ocorra para determinada geração, independentemente do estado da coleção atual de lixo.</span><span class="sxs-lookup"><span data-stu-id="57938-111">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>|  
|[<span data-ttu-id="57938-112">Método GetStats</span><span class="sxs-lookup"><span data-stu-id="57938-112">GetStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|<span data-ttu-id="57938-113">Obtém as estatísticas para o estado atual do sistema de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="57938-113">Gets the statistics for the current state of the garbage collection system.</span></span>|  
|[<span data-ttu-id="57938-114">Método GetThreadStats</span><span class="sxs-lookup"><span data-stu-id="57938-114">GetThreadStats Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|<span data-ttu-id="57938-115">Obtém as estatísticas por thread de coleta de lixo.</span><span class="sxs-lookup"><span data-stu-id="57938-115">Gets the per-thread statistics for garbage collection.</span></span>|  
|[<span data-ttu-id="57938-116">Método SetGCStartupLimits</span><span class="sxs-lookup"><span data-stu-id="57938-116">SetGCStartupLimits Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|<span data-ttu-id="57938-117">Define o tamanho do segmento e o tamanho máximo de geração 0.</span><span class="sxs-lookup"><span data-stu-id="57938-117">Sets the segment size and the maximum size for generation 0.</span></span>|  
|[<span data-ttu-id="57938-118">Método SetVirtualMemLimit</span><span class="sxs-lookup"><span data-stu-id="57938-118">SetVirtualMemLimit Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|<span data-ttu-id="57938-119">Define o tamanho máximo de memória virtual do tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="57938-119">Sets the maximum size of the runtime's virtual memory.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57938-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57938-120">Requirements</span></span>  
 <span data-ttu-id="57938-121">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57938-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57938-122">**Cabeçalho:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="57938-122">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="57938-123">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="57938-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57938-124">**Versões do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57938-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57938-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="57938-125">See Also</span></span>  
 [<span data-ttu-id="57938-126">Interfaces de hospedagem</span><span class="sxs-lookup"><span data-stu-id="57938-126">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="57938-127">Coclass CorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="57938-127">CorRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)