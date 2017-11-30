---
title: 117 - WorkflowInstanceTerminatedRecordWithId
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e68539d0-5338-468a-9f75-7e5b09d39a3c
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: c8b2bc6325ec6f5cf1c3af8b7748a45ad21809cd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2017
---
# <a name="117---workflowinstanceterminatedrecordwithid"></a><span data-ttu-id="46808-102">117 - WorkflowInstanceTerminatedRecordWithId</span><span class="sxs-lookup"><span data-stu-id="46808-102">117 - WorkflowInstanceTerminatedRecordWithId</span></span>
## <a name="properties"></a><span data-ttu-id="46808-103">Propriedades</span><span class="sxs-lookup"><span data-stu-id="46808-103">Properties</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="46808-104">ID</span><span class="sxs-lookup"><span data-stu-id="46808-104">ID</span></span>|<span data-ttu-id="46808-105">117</span><span class="sxs-lookup"><span data-stu-id="46808-105">117</span></span>|  
|<span data-ttu-id="46808-106">Palavras-chave</span><span class="sxs-lookup"><span data-stu-id="46808-106">Keywords</span></span>|<span data-ttu-id="46808-107">HealthMonitoring, WFTracking</span><span class="sxs-lookup"><span data-stu-id="46808-107">HealthMonitoring, WFTracking</span></span>|  
|<span data-ttu-id="46808-108">Nível</span><span class="sxs-lookup"><span data-stu-id="46808-108">Level</span></span>|<span data-ttu-id="46808-109">Erro</span><span class="sxs-lookup"><span data-stu-id="46808-109">Error</span></span>|  
|<span data-ttu-id="46808-110">Canal</span><span class="sxs-lookup"><span data-stu-id="46808-110">Channel</span></span>|<span data-ttu-id="46808-111">Os aplicativos de servidor de Microsoft-Windows- aplicativo/analítico</span><span class="sxs-lookup"><span data-stu-id="46808-111">Microsoft-Windows-Application Server-Applications/Analytic</span></span>|  
  
## <a name="description"></a><span data-ttu-id="46808-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="46808-112">Description</span></span>  
 <span data-ttu-id="46808-113">Este evento é emitido pelo participante de rastreamento de ETW quando uma instância de fluxo de trabalho se emite WorkflowInstanceTerminatedRecord.</span><span class="sxs-lookup"><span data-stu-id="46808-113">This event is emitted by the ETW tracking participant when a workflow instance emits WorkflowInstanceTerminatedRecord.</span></span>  
  
## <a name="message"></a><span data-ttu-id="46808-114">Mensagem</span><span class="sxs-lookup"><span data-stu-id="46808-114">Message</span></span>  
 <span data-ttu-id="46808-115">TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, motivo = %5, anotações = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span><span class="sxs-lookup"><span data-stu-id="46808-115">TrackRecord = WorkflowInstanceTerminatedRecord, InstanceID = %1, RecordNumber = %2, EventTime = %3, ActivityDefinitionId = %4, Reason = %5,  Annotations = %6, ProfileName = %7, WorkflowDefinitionIdentity = %8</span></span>  
  
## <a name="details"></a><span data-ttu-id="46808-116">Detalhes</span><span class="sxs-lookup"><span data-stu-id="46808-116">Details</span></span>  
  
|<span data-ttu-id="46808-117">Nome do item de dados</span><span class="sxs-lookup"><span data-stu-id="46808-117">Data Item Name</span></span>|<span data-ttu-id="46808-118">Tipo de item de dados</span><span class="sxs-lookup"><span data-stu-id="46808-118">Data Item Type</span></span>|<span data-ttu-id="46808-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="46808-119">Description</span></span>|  
|--------------------|--------------------|-----------------|  
|<span data-ttu-id="46808-120">InstanceId</span><span class="sxs-lookup"><span data-stu-id="46808-120">InstanceId</span></span>|<span data-ttu-id="46808-121">xs:GUID</span><span class="sxs-lookup"><span data-stu-id="46808-121">xs:GUID</span></span>|<span data-ttu-id="46808-122">A identificação de instância para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="46808-122">The instance id for the workflow</span></span>|  
|<span data-ttu-id="46808-123">RecordNumber</span><span class="sxs-lookup"><span data-stu-id="46808-123">RecordNumber</span></span>|<span data-ttu-id="46808-124">xs:long</span><span class="sxs-lookup"><span data-stu-id="46808-124">xs:long</span></span>|<span data-ttu-id="46808-125">O número de sequência do registro emitido</span><span class="sxs-lookup"><span data-stu-id="46808-125">The sequence number of the emitted record</span></span>|  
|<span data-ttu-id="46808-126">EventTime</span><span class="sxs-lookup"><span data-stu-id="46808-126">EventTime</span></span>|<span data-ttu-id="46808-127">xs:dateTime</span><span class="sxs-lookup"><span data-stu-id="46808-127">xs:dateTime</span></span>|<span data-ttu-id="46808-128">A hora UTC quando o evento foi emitido</span><span class="sxs-lookup"><span data-stu-id="46808-128">The time in UTC when the event was emitted</span></span>|  
|<span data-ttu-id="46808-129">ActivityDefinitionId</span><span class="sxs-lookup"><span data-stu-id="46808-129">ActivityDefinitionId</span></span>|<span data-ttu-id="46808-130">xs:string</span><span class="sxs-lookup"><span data-stu-id="46808-130">xs:string</span></span>|<span data-ttu-id="46808-131">O nome da atividade raiz no fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="46808-131">The name of the root activity in the workflow</span></span>|  
|<span data-ttu-id="46808-132">Estado</span><span class="sxs-lookup"><span data-stu-id="46808-132">State</span></span>|<span data-ttu-id="46808-133">xs:string</span><span class="sxs-lookup"><span data-stu-id="46808-133">xs:string</span></span>|<span data-ttu-id="46808-134">O estado atual de fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="46808-134">The current state of the Workflow.</span></span>|  
|<span data-ttu-id="46808-135">Anotações</span><span class="sxs-lookup"><span data-stu-id="46808-135">Annotations</span></span>|<span data-ttu-id="46808-136">xs:string</span><span class="sxs-lookup"><span data-stu-id="46808-136">xs:string</span></span>|<span data-ttu-id="46808-137">As anotações que foram adicionadas a este evento.</span><span class="sxs-lookup"><span data-stu-id="46808-137">The annotations that were added to this event.</span></span> <span data-ttu-id="46808-138">Os valores são armazenados em um elemento xml no formato \<itens >\< nome do item = "annotationName" type="System.String" > annotationValue\</item > \< /itens >.</span><span class="sxs-lookup"><span data-stu-id="46808-138">The values are stored in an xml element in the format \<items>\< item name = "annotationName" type="System.String">annotationValue\</item>\</items>.</span></span> <span data-ttu-id="46808-139">Se nenhuma anotação é especificada, em seguida, a cadeia de caracteres contém \<itens / >.</span><span class="sxs-lookup"><span data-stu-id="46808-139">If no annotations are specified then the string contains \<items/>.</span></span> <span data-ttu-id="46808-140">O tamanho do evento de ETW é limitado pelo tamanho do buffer de ETW ou pela carga máxima útil para um evento de ETW.</span><span class="sxs-lookup"><span data-stu-id="46808-140">The ETW event size is limited by the ETW buffer size or the max payload for an ETW event.</span></span> <span data-ttu-id="46808-141">Se o tamanho do evento excede os limites ETW, o evento é truncado descartando as anotações e substituindo o valor anotação com \<itens >...  \< /itens >.</span><span class="sxs-lookup"><span data-stu-id="46808-141">If the size of the event exceeds the ETW limits, then the event is truncated by dropping the annotations and replacing the annotation value with \<items>...\</items>.</span></span>|  
|<span data-ttu-id="46808-142">ProfileName</span><span class="sxs-lookup"><span data-stu-id="46808-142">ProfileName</span></span>|<span data-ttu-id="46808-143">xs:string</span><span class="sxs-lookup"><span data-stu-id="46808-143">xs:string</span></span>|<span data-ttu-id="46808-144">O nome ou o perfil de rastreamento que levam a este evento que está sendo emitido</span><span class="sxs-lookup"><span data-stu-id="46808-144">The name or the tracking profile that resulted in this event being emitted</span></span>|  
|<span data-ttu-id="46808-145">WorkflowDefinitionIdentity</span><span class="sxs-lookup"><span data-stu-id="46808-145">WorkflowDefinitionIdentity</span></span>|<span data-ttu-id="46808-146">xs:string</span><span class="sxs-lookup"><span data-stu-id="46808-146">xs:string</span></span>|<span data-ttu-id="46808-147">A identificação da definição de fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="46808-147">The workflow definition id</span></span>|  
|<span data-ttu-id="46808-148">AppDomain</span><span class="sxs-lookup"><span data-stu-id="46808-148">AppDomain</span></span>|<span data-ttu-id="46808-149">xs:string</span><span class="sxs-lookup"><span data-stu-id="46808-149">xs:string</span></span>|<span data-ttu-id="46808-150">A cadeia de caracteres retornada por AppDomain.CurrentDomain.FriendlyName.</span><span class="sxs-lookup"><span data-stu-id="46808-150">The string returned by AppDomain.CurrentDomain.FriendlyName.</span></span>|