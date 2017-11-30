---
title: "Método ICorRuntimeHost::SwitchOutLogicalThreadState"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.SwitchOutLogicalThreadState
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::SwitchOutLogicalThreadState
helpviewer_keywords:
- ICorRuntimeHost::SwitchOutLogicalThreadState method [.NET Framework hosting]
- SwitchOutLogicalThreadState method [.NET Framework hosting]
ms.assetid: e1968f0b-2675-4dc2-8507-46164e1df154
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 9eed11dd0a5ebd30952946f640957e9960485524
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="icorruntimehostswitchoutlogicalthreadstate-method"></a><span data-ttu-id="61e29-102">Método ICorRuntimeHost::SwitchOutLogicalThreadState</span><span class="sxs-lookup"><span data-stu-id="61e29-102">ICorRuntimeHost::SwitchOutLogicalThreadState Method</span></span>
<span data-ttu-id="61e29-103">Esse método oferece suporte a infraestrutura do .NET Framework e não se destina a ser usado diretamente do seu código.</span><span class="sxs-lookup"><span data-stu-id="61e29-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61e29-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="61e29-104">Syntax</span></span>  
  
```  
HRESULT SwitchOutLogicalThreadState(  
    [out] DWORD **pFiberCookie  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="61e29-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="61e29-105">Parameters</span></span>  
 `pFiberCookie`  
 <span data-ttu-id="61e29-106">[out] Cookie que indica a fibra sendo alternada.</span><span class="sxs-lookup"><span data-stu-id="61e29-106">[out] Cookie that indicates the fiber being switched out.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61e29-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61e29-107">Requirements</span></span>  
 <span data-ttu-id="61e29-108">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61e29-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61e29-109">**Cabeçalho:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="61e29-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61e29-110">**Biblioteca:** incluído como um recurso no MSCOREE</span><span class="sxs-lookup"><span data-stu-id="61e29-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61e29-111">**Versão do .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="61e29-111">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61e29-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="61e29-112">See Also</span></span>  
 [<span data-ttu-id="61e29-113">Interface ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="61e29-113">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)