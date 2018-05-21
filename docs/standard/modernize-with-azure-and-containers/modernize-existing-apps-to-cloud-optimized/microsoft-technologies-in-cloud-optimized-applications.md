---
title: Tecnologias da Microsoft em aplicativos com otimização de nuvem
description: Modernizar aplicativos existentes do .NET com contêineres do Windows e de nuvem do Azure | Tecnologias da Microsoft em aplicativos com otimização de nuvem
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: ece366ee3918124bb60e367d3c7447c1d4555c72
ms.sourcegitcommit: 88f251b08bf0718ce119f3d7302f514b74895038
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2018
---
# <a name="microsoft-technologies-in-cloud-optimized-applications"></a><span data-ttu-id="50ada-103">Tecnologias da Microsoft em aplicativos com otimização de nuvem</span><span class="sxs-lookup"><span data-stu-id="50ada-103">Microsoft technologies in cloud-optimized applications</span></span>

<span data-ttu-id="50ada-104">A lista a seguir descreve as ferramentas, tecnologias e soluções que são reconhecidas como os requisitos para aplicativos otimizada para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="50ada-104">The following list describes the tools, technologies, and solutions that are recognized as requirements for Cloud-Optimized apps.</span></span> <span data-ttu-id="50ada-105">Você pode adotar otimizada para a nuvem elementos seletivamente ou gradualmente, dependendo de suas prioridades.</span><span class="sxs-lookup"><span data-stu-id="50ada-105">You can adopt Cloud-Optimized elements selectively or gradually, depending on your priorities.</span></span>

-   <span data-ttu-id="50ada-106">**Infraestrutura de nuvem**: A infraestrutura que fornece a plataforma de computação, sistema operacional, rede e armazenamento.</span><span class="sxs-lookup"><span data-stu-id="50ada-106">**Cloud infrastructure**: The infrastructure that provides the compute platform, operating system, network, and storage.</span></span> <span data-ttu-id="50ada-107">Microsoft Azure está posicionado nesse nível.</span><span class="sxs-lookup"><span data-stu-id="50ada-107">Microsoft Azure is positioned at this level.</span></span>

-   <span data-ttu-id="50ada-108">**Tempo de execução**: essa camada fornece o ambiente para o aplicativo seja executado.</span><span class="sxs-lookup"><span data-stu-id="50ada-108">**Runtime**: This layer provides the environment for the application to run.</span></span> <span data-ttu-id="50ada-109">Se você estiver usando contêineres, essa camada geralmente é baseada em [mecanismo do Docker](https://docs.docker.com/engine/), em execução em hosts Linux ou em hosts do Windows.</span><span class="sxs-lookup"><span data-stu-id="50ada-109">If you are using containers, this layer usually is based on [Docker Engine](https://docs.docker.com/engine/), running either on Linux hosts or on Windows hosts.</span></span> <span data-ttu-id="50ada-110">([Contêineres do Windows](https://docs.microsoft.com/virtualization/windowscontainers/about/) têm suporte começando com o Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="50ada-110">([Windows Containers](https://docs.microsoft.com/virtualization/windowscontainers/about/) are supported beginning with Windows Server 2016.</span></span> <span data-ttu-id="50ada-111">Contêineres do Windows é a melhor escolha para aplicativos existentes do .NET Framework que são executados no Windows.)</span><span class="sxs-lookup"><span data-stu-id="50ada-111">Windows Containers is the best choice for existing .NET Framework applications that run on Windows.)</span></span>

-   <span data-ttu-id="50ada-112">**Gerenciado nuvem**: quando você escolher uma opção de nuvem gerenciado, você pode evitar a despesa e complexidade do gerenciamento e os patches de sistema operacional subjacentes infraestrutura, máquinas virtuais, de suporte e configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="50ada-112">**Managed cloud**: When you choose a managed cloud option, you can avoid the expense and complexity of managing and supporting the underlying infrastructure, VMs, OS patches, and networking configuration.</span></span> <span data-ttu-id="50ada-113">Se você optar por migrar usando IaaS, você é responsável para todas as tarefas e os custos associados.</span><span class="sxs-lookup"><span data-stu-id="50ada-113">If you choose to migrate by using IaaS, you are responsible for all of these tasks, and for associated costs.</span></span> <span data-ttu-id="50ada-114">Uma opção de nuvem gerenciado, você pode gerenciar apenas os aplicativos e serviços que você desenvolve.</span><span class="sxs-lookup"><span data-stu-id="50ada-114">In a managed cloud option, you manage only the applications and services that you develop.</span></span> <span data-ttu-id="50ada-115">O provedor de serviços de nuvem normalmente gerencia todo o resto.</span><span class="sxs-lookup"><span data-stu-id="50ada-115">The cloud service provider typically manages everything else.</span></span> <span data-ttu-id="50ada-116">Exemplos de serviços de nuvem gerenciados no Azure [banco de dados do SQL Azure](https://azure.microsoft.com/services/sql-database), [Cache Redis do Azure](https://azure.microsoft.com/services/cache/), [o banco de dados do Azure Cosmos](https://azure.microsoft.com/services/cosmos-db/), [armazenamento do Azure](https://azure.microsoft.com/services/storage/), [Banco de dados do azure para MySQL](https://azure.microsoft.com/services/mysql/), [banco de dados do Azure para PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Active Directory do Azure](https://azure.microsoft.com/services/active-directory/)e os serviços de computação como gerenciados [escalas de VM define](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [do serviço de aplicativo do Azure](https://azure.microsoft.com/services/app-service/), e [o serviço do Azure Kubernetes](https://azure.microsoft.com/services/container-service/).</span><span class="sxs-lookup"><span data-stu-id="50ada-116">Examples of managed cloud services in Azure include [Azure SQL Database](https://azure.microsoft.com/services/sql-database), [Azure Redis Cache](https://azure.microsoft.com/services/cache/), [Azure Cosmos DB](https://azure.microsoft.com/services/cosmos-db/), [Azure Storage](https://azure.microsoft.com/services/storage/), [Azure Database for MySQL](https://azure.microsoft.com/services/mysql/), [Azure Database for PostgreSQL](https://azure.microsoft.com/services/postgresql/), [Azure Active Directory](https://azure.microsoft.com/services/active-directory/), and managed compute services like [VM scale sets](https://azure.microsoft.com/services/virtual-machine-scale-sets/), [Azure Service Fabric](https://azure.microsoft.com/services/service-fabric/), [Azure App Service](https://azure.microsoft.com/services/app-service/), and [Azure Kubernetes Service](https://azure.microsoft.com/services/container-service/).</span></span>

-   <span data-ttu-id="50ada-117">**Desenvolvimento de aplicativos**: você pode escolher entre vários idiomas quando você criar aplicativos que são executados em contêineres.</span><span class="sxs-lookup"><span data-stu-id="50ada-117">**Application development**: You can choose from many languages when you build applications that run in containers.</span></span> <span data-ttu-id="50ada-118">Este guia se concentra em [.NET](https://www.microsoft.com/net), mas você pode desenvolver aplicativos baseados no contêiner por meio de outras linguagens, como Node.js, Python, Spring/Java, ou vá.</span><span class="sxs-lookup"><span data-stu-id="50ada-118">This guide focuses on [.NET](https://www.microsoft.com/net), but, you can develop container-based apps by using other languages, like Node.js, Python, Spring/Java, or Go.</span></span>

-   <span data-ttu-id="50ada-119">**Monitoramento de telemetria, registro em log e auditoria**: A capacidade de auditoria e monitorar aplicativos e contêineres que estão em execução na nuvem é essencial para qualquer aplicativo otimizada para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="50ada-119">**Monitoring, telemetry, logging, and auditing**: The ability to monitor and audit applications and containers that are running in the cloud is critical for any Cloud-Optimized application.</span></span> <span data-ttu-id="50ada-120">[Informações de aplicativo do Azure](https://azure.microsoft.com/services/application-insights/) e [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) são as principais ferramentas da Microsoft que fornecem monitoramento e auditoria para aplicativos otimizada para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="50ada-120">[Azure Application Insights](https://azure.microsoft.com/services/application-insights/) and [Microsoft Operations Management Suite](https://www.microsoft.com/cloud-platform/operations-management-suite) are the main Microsoft tools that provide monitoring and auditing for Cloud-Optimized apps.</span></span>

-   <span data-ttu-id="50ada-121">**Provisionamento**: ferramentas de automação ajudarão-lo a provisionar a infraestrutura e implantar um aplicativo em vários ambientes (produção, teste, preparação).</span><span class="sxs-lookup"><span data-stu-id="50ada-121">**Provisioning**: Automation tools help you provision the infrastructure and deploy an application to multiple environments (production, testing, staging).</span></span> <span data-ttu-id="50ada-122">Você pode usar ferramentas como o Chef e Puppet para gerenciar o ambiente e a configuração de um aplicativo.</span><span class="sxs-lookup"><span data-stu-id="50ada-122">You can use tools like Chef and Puppet to manage an application's configuration and environment.</span></span> <span data-ttu-id="50ada-123">Essa camada também pode ser implementada por meio de abordagens mais simples e mais diretas.</span><span class="sxs-lookup"><span data-stu-id="50ada-123">This layer also can be implemented by using simpler and more direct approaches.</span></span> <span data-ttu-id="50ada-124">Por exemplo, você pode implantar diretamente usando a interface de linha de comando do Azure (Azure CLI) ferramentas e, em seguida, usar a implantação contínua e pipelines de gerenciamento de versão [do Visual Studio Team Services](https://www.visualstudio.com/team-services/).</span><span class="sxs-lookup"><span data-stu-id="50ada-124">For example, you can deploy directly by using Azure command-line interface (Azure CLI) tooling, and then use the continuous deployment and release management pipelines in [Visual Studio Team Services](https://www.visualstudio.com/team-services/).</span></span>

-   <span data-ttu-id="50ada-125">**Ciclo de vida do aplicativo**: [do Visual Studio Team Services](https://www.visualstudio.com/team-services/) e outras ferramentas, como Jenkins, são servidores de automação criada que ajudarão-lo a implementar pipelines CI/CD, incluindo o gerenciamento de versão.</span><span class="sxs-lookup"><span data-stu-id="50ada-125">**Application lifecycle**: [Visual Studio Team Services](https://www.visualstudio.com/team-services/) and other tools, like Jenkins, are built automation servers that help you implement CI/CD pipelines, including release management.</span></span>

<span data-ttu-id="50ada-126">As próximas seções deste capítulo e o passo a passo relacionado, concentre-se especificamente nos detalhes sobre a camada de tempo de execução (contêineres do Windows).</span><span class="sxs-lookup"><span data-stu-id="50ada-126">The next sections of this chapter, and the related walkthroughs, focus specifically on details about the runtime layer (Windows Containers).</span></span> <span data-ttu-id="50ada-127">O guia descreve as maneiras como você pode implantar contêineres do Windows no Windows Server 2016 (e versões posteriores) VMs e instâncias de contêiner do Azure.</span><span class="sxs-lookup"><span data-stu-id="50ada-127">The guidance describes the ways you can deploy Windows Containers on Windows Server 2016 (and later versions) VMs and Azure Container Instances.</span></span> <span data-ttu-id="50ada-128">Ele também aborda plataformas mais avançadas de PaaS como o serviço de aplicativo do Azure e o orchestrator como Kubernetes o serviço do Azure e o Azure Service Fabric.</span><span class="sxs-lookup"><span data-stu-id="50ada-128">It also covers more advanced PaaS platforms like Azure App Service and orchestrator like Azure Service Fabric and Azure Kubernetes Service.</span></span>

## <a name="monolithic-applications-can-be-cloud-optimized"></a><span data-ttu-id="50ada-129">Aplicativos monolíticos *pode* ser otimizada para a nuvem</span><span class="sxs-lookup"><span data-stu-id="50ada-129">Monolithic applications *can* be Cloud-Optimized</span></span>

<span data-ttu-id="50ada-130">É importante destacar que monolítico aplicativos (que não são baseados em microservices) *pode* ser otimizada para a nuvem de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="50ada-130">It's important to highlight that monolithic applications (applications that are not based on microservices) *can* be Cloud-Optimized applications.</span></span> <span data-ttu-id="50ada-131">Você pode criar e operar monolíticos aplicativos que aproveitam a modelo de computação usando uma combinação de contêineres, fornecimento contínuo e DevOps em nuvem.</span><span class="sxs-lookup"><span data-stu-id="50ada-131">You can build and operate monolithic applications that take advantage of the cloud computing model by using a combination of containers, continuous delivery, and DevOps.</span></span> <span data-ttu-id="50ada-132">Se um aplicativo monolítico existente é adequado para suas metas de negócios, você pode modernizá-lo e torná-lo otimizada para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="50ada-132">If an existing monolithic application is right for your business goals, you can modernize it and make it Cloud-Optimized.</span></span>

<span data-ttu-id="50ada-133">Da mesma forma, se monolítico aplicativos podem ser aplicativos otimizada para a nuvem, outras arquiteturas mais complexas como aplicativos de N camadas podem ser modernizadas como aplicativos otimizada para a nuvem.</span><span class="sxs-lookup"><span data-stu-id="50ada-133">Similarly, if monolithic applications can be Cloud-Optimized applications, other, more complex architectures like N-Tier applications can also be modernized as Cloud-Optimized applications.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="50ada-134">[Anterior](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[Próximo](what-about-cloud-native-applications.md)</span><span class="sxs-lookup"><span data-stu-id="50ada-134">[Previous](reasons-to-modernize-existing-net-apps-to-cloud-optimized-applications.md)
[Next](what-about-cloud-native-applications.md)</span></span>