---
title: "疑难解答： 服务应用程序赢得 &#39; 无法安装"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- troubleshooting service applications
- services, troubleshooting
- services, debugging
- Windows NT services, troubleshooting
- troubleshooting NT services
- Windows Service applications, troubleshooting
ms.assetid: 45c48e2e-b97d-44bc-8896-14f328e0ce33
caps.latest.revision: "8"
author: ghogen
ms.author: ghogen
manager: douge
ms.openlocfilehash: 82eb870761a7865385631cd9961ce99e0b0d3502
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="troubleshooting-service-application-won39t-install"></a><span data-ttu-id="e54a2-102">疑难解答： 服务应用程序赢得 &#39; 无法安装</span><span class="sxs-lookup"><span data-stu-id="e54a2-102">Troubleshooting: Service Application Won&#39;t Install</span></span>
<span data-ttu-id="e54a2-103">如果服务应用程序将无法正确安装，请检查以确保<xref:System.ServiceProcess.ServiceBase.ServiceName%2A>为服务类的属性设置为相同的值，该服务的安装程序中所示。</span><span class="sxs-lookup"><span data-stu-id="e54a2-103">If your service application will not install correctly, check to make sure that the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> property for the service class is set to the same value as is shown in the installer for that service.</span></span> <span data-ttu-id="e54a2-104">值必须是为了使你的服务以正确安装两个实例中相同。</span><span class="sxs-lookup"><span data-stu-id="e54a2-104">The value must be the same in both instances in order for your service to install correctly.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e54a2-105">你还可以查看安装日志，以在安装过程中获得反馈。</span><span class="sxs-lookup"><span data-stu-id="e54a2-105">You can also look at the installation logs to get feedback on the installation process.</span></span>  
  
 <span data-ttu-id="e54a2-106">你还应检查来确定是否有另一个服务具有相同的名称已安装。</span><span class="sxs-lookup"><span data-stu-id="e54a2-106">You should also check to determine whether you have another service with the same name already installed.</span></span> <span data-ttu-id="e54a2-107">服务名称必须唯一，安装才能成功。</span><span class="sxs-lookup"><span data-stu-id="e54a2-107">Service names must be unique for installation to succeed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e54a2-108">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e54a2-108">See Also</span></span>  
 [<span data-ttu-id="e54a2-109">Windows 服务应用程序简介</span><span class="sxs-lookup"><span data-stu-id="e54a2-109">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
