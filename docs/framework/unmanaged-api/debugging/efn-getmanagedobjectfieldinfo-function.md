---
title: "Função _EFN_GetManagedObjectFieldInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _EFN_GetManagedObjectFieldInfo
api_location: mscordbi.dll
api_type: COM
f1_keywords: _EFN_GetManagedObjectFieldInfo
helpviewer_keywords: _EFN_GetManagedObjectFieldInfo function [.NET Framework debugging]
ms.assetid: 3b93bcff-62a4-47b2-babc-6bcf4216119a
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c3df09c9107b683381f21891a1001140c493a024
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="efngetmanagedobjectfieldinfo-function"></a><span data-ttu-id="babd1-102">Função _EFN_GetManagedObjectFieldInfo</span><span class="sxs-lookup"><span data-stu-id="babd1-102">_EFN_GetManagedObjectFieldInfo Function</span></span>
<span data-ttu-id="babd1-103">Obtém o deslocamento do início de um objeto para um campo e o valor do campo, usando o ponteiro de objeto fornecido e o nome do campo.</span><span class="sxs-lookup"><span data-stu-id="babd1-103">Gets the offset from the start of an object to a field and the field's value, using the provided object pointer and field name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="babd1-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="babd1-104">Syntax</span></span>  
  
```  
HRESULT _EFN_GetManagedObjectFieldInfo(  
    [in]  PDEBUG_CLIENT Client,  
    [in]  ULONG64       objAddr,  
    [in]  __out_ecount (mdNameLen) PSTR szFieldName,  
    [out] PULONG64      pValue,  
    [out] PULONG        pOffset  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="babd1-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="babd1-105">Parameters</span></span>  
 `Client`  
 <span data-ttu-id="babd1-106">[in] Um ponteiro para o cliente de depuração.</span><span class="sxs-lookup"><span data-stu-id="babd1-106">[in] A pointer to the debug client.</span></span>  
  
 `objAddr`  
 <span data-ttu-id="babd1-107">[in] Um ponteiro de objeto gerenciado.</span><span class="sxs-lookup"><span data-stu-id="babd1-107">[in] A managed object pointer.</span></span>  
  
 <span data-ttu-id="babd1-108">szFieldName</span><span class="sxs-lookup"><span data-stu-id="babd1-108">szFieldName</span></span>  
 <span data-ttu-id="babd1-109">[in] Um ponteiro de objeto gerenciado para o nome do campo.</span><span class="sxs-lookup"><span data-stu-id="babd1-109">[in] A managed object pointer to the field name.</span></span>  
  
 `pValue`  
 <span data-ttu-id="babd1-110">[out] O valor do campo.</span><span class="sxs-lookup"><span data-stu-id="babd1-110">[out] The field value.</span></span> <span data-ttu-id="babd1-111">Este parâmetro pode ser nulo.</span><span class="sxs-lookup"><span data-stu-id="babd1-111">This parameter can be null.</span></span>  
  
 `pOffset`  
 <span data-ttu-id="babd1-112">[out] O deslocamento do `objAddr` ao campo.</span><span class="sxs-lookup"><span data-stu-id="babd1-112">[out] The offset from `objAddr` to the field.</span></span> <span data-ttu-id="babd1-113">Este parâmetro pode ser nulo.</span><span class="sxs-lookup"><span data-stu-id="babd1-113">This parameter can be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="babd1-114">Comentários</span><span class="sxs-lookup"><span data-stu-id="babd1-114">Remarks</span></span>  
 <span data-ttu-id="babd1-115">Se o deslocamento for 0, o deslocamento não é gravado.</span><span class="sxs-lookup"><span data-stu-id="babd1-115">If the offset is 0, no offset is written.</span></span>  
  
 <span data-ttu-id="babd1-116">Não se houver nenhum código gerenciado no thread no momento no contexto, a função retorna o HRESULT SOS_E_NOMANAGEDCODE com um valor de recurso de 0xa0 e um código de erro de 0x1000.</span><span class="sxs-lookup"><span data-stu-id="babd1-116">If there is no managed code on the thread currently in context, the function returns HRESULT SOS_E_NOMANAGEDCODE with a facility value of 0xa0 and an error code of 0x1000.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="babd1-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="babd1-117">Requirements</span></span>  
 <span data-ttu-id="babd1-118">**Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="babd1-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="babd1-119">**Cabeçalho:** SOS_Stacktrace.h</span><span class="sxs-lookup"><span data-stu-id="babd1-119">**Header:** SOS_Stacktrace.h</span></span>  
  
 <span data-ttu-id="babd1-120">**Versão do .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="babd1-120">**.NET Framework Version:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="babd1-121">Consulte também</span><span class="sxs-lookup"><span data-stu-id="babd1-121">See Also</span></span>  
 [<span data-ttu-id="babd1-122">Depurando funções estáticas globais</span><span class="sxs-lookup"><span data-stu-id="babd1-122">Debugging Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)