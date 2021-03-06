---
title: Método ICorDebugILFrame2::RemapFunction
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame2.RemapFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame2::RemapFunction
helpviewer_keywords:
- ICorDebugILFrame2::RemapFunction method [.NET Framework debugging]
- RemapFunction method [.NET Framework debugging]
ms.assetid: dd639ba0-f77b-426d-9ff6-f92706840348
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9f03d8c993be1ac83ca84275bcb94f1bb3cdf884
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414977"
---
# <a name="icordebugilframe2remapfunction-method"></a>Método ICorDebugILFrame2::RemapFunction
Remapeia uma função editada, especificando o novo deslocamento de linguagem intermediária (MSIL) Microsoft  
  
## <a name="syntax"></a>Sintaxe  
  
```  
HRESULT RemapFunction (  
    [in] ULONG32      newILOffset  
);  
```  
  
#### <a name="parameters"></a>Parâmetros  
 `newILOffset`  
 [in] Novo MSIL deslocamento do quadro de pilhas em que o ponteiro de instrução deve ser colocado. Esse valor deve ser um ponto de sequência.  
  
 É responsabilidade do chamador para garantir a validade do valor. Por exemplo, o deslocamento do MSIL não é válido se ele está fora dos limites da função.  
  
## <a name="remarks"></a>Comentários  
 Quando a função do quadro foi editada, o depurador pode chamar o `RemapFunction` método alternar a versão mais recente da função do quadro para que ele pode ser executado. A execução de código será iniciado em um deslocamento específico do MSIL.  
  
> [!NOTE]
>  Chamando `RemapFunction`, como chamar [Icordebugilframe](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-setip-method.md), imediatamente invalidará todas as interfaces de depuração que estão relacionadas à geração de um rastreamento de pilha do thread. Essas interfaces incluem [ICorDebugChain](../../../../docs/framework/unmanaged-api/debugging/icordebugchain-interface.md), ICorDebugILFrame, ICorDebugInternalFrame e ICorDebugNativeFrame.  
  
 O `RemapFunction` método pode ser chamado somente no contexto do quadro atual e somente em um dos seguintes casos:  
  
-   Após o recebimento de uma [Icordebugmanagedcallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md) retorno de chamada que não tenha sido continuado.  
  
-   Enquanto a execução de código é interrompida por uma [: Editandcontinueremap](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md) eventos para este quadro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** consulte [requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versões do .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
