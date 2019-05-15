---
title: 部署 WCF 库项目
ms.date: 03/30/2017
ms.assetid: 9f9222fe-d358-443c-9a49-12c5498e35e7
ms.openlocfilehash: 0400fc9ec5a5629139348709bbd3a5554ce251c7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593351"
---
# <a name="deploying-a-wcf-library-project"></a>部署 WCF 库项目
本主题介绍如何部署 Windows Communication Foundation (WCF) 服务库项目。  
  
## <a name="deploying-a-wcf-service-library"></a>部署 WCF 服务库  
 WCF 服务库是一个动态链接库 (DLL)。 因此，它不能自己运行。 必须将其部署到宿主环境中。 有关此过程的详细信息，请参阅[托管和使用 WCF 服务](https://go.microsoft.com/fwlink/?LinkId=99932)。  
  
 可以像任何其他 WCF 服务一样部署的 WCF 服务库。 但是，请注意，.NET Framework 不支持配置的 Dll。 <xref:System.Configuration> 支持每个应用程序域一个配置文件。 WCF 服务库项目通过在开发期间提供库的 App.config 文件来减少此限制。 但在部署之后不能识别 App.config 文件。  
  
 必须将配置代码移动到主机环境所识别的配置文件中。 对于自承载，您应将 App.config 文件的内容复制到宿主可执行文件的 App.config 文件中。 如果使用 IIS 承载服务，则应将 App.config 文件的内容复制到虚拟目录的 Web.config 文件中。
