---
title: Função BeginMethodEnumeration (referência de API não gerenciada)
description: A função BeginMethodEnumeration inicia uma enumeração dos métodos do objeto
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e69625184aca7d1ebd4bb0b7dc7c4958596b906a
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/27/2018
ms.locfileid: "43000337"
---
# <a name="beginenumeration-function"></a>Função BeginEnumeration
Inicia uma enumeração dos métodos disponíveis para o objeto.  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintaxe  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a>Parâmetros

`vFunc`  
[in] Esse parâmetro é usado.

`ptr`  
[in] Um ponteiro para um [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instância.

`lEnumFlags`  
[in] Zero (0) para todos os métodos, ou um sinalizador que especifica o escopo da enumeração. Os seguintes sinalizadores são definidos na *WbemCli.h* arquivo de cabeçalho, ou você pode defini-los como constantes em seu código:

Constante  |Valor  |Descrição  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | 0x10 | Limite a enumeração para os métodos que são definidos na própria classe. |
| `WBEM_FLAG_PROPAGATED_ONLY` |  0x20 | Limite a enumeração para propriedades que são herdadas de classes base. |

## <a name="return-value"></a>Valor retornado

Os seguintes valores retornados por essa função são definidos na *WbemCli.h* arquivo de cabeçalho, ou você pode defini-los como constantes em seu código:

|Constante  |Valor  |Descrição  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | `lEnnumFlags` é diferente de zero e não é um dos sinalizadores especificados. |
|`WBEM_S_NO_ERROR` | 0 | A chamada de função foi bem-sucedida.  |
  
## <a name="remarks"></a>Comentários

Essa função encapsula uma chamada para o [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) método.

Somente há suporte para esta chamada de método se o objeto atual é uma definição de classe. Manipulação de método não está disponível no [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ponteiros que apontam para as instâncias. A ordem na qual os métodos são enumerados é garantida para ser invariável para uma determinada instância do [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).

## <a name="requirements"></a>Requisitos  
 **Plataformas:** confira [Requisitos do sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Cabeçalho:** WMINet_Utils.idl  
  
 **Versões do .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Consulte também  
[WMI e contadores de desempenho (referência de API não gerenciada)](index.md)
