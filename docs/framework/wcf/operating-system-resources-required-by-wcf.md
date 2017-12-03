---
title: "WCF 所要求的操作系统资源"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 31006331f5e8a71bf3f4fb9a68c31cb32d0b6f2b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="operating-system-resources-required-by-wcf"></a>WCF 所要求的操作系统资源
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 的正常运行依赖于操作系统提供的几种资源。 下表列出了这些资源。  
  
|资源|描述|  
|--------------|-----------------|  
|Microsoft 分布式事务协调器 (MSDTC)|支持 OleTx 事务所必需。|  
|Internet 信息服务 (IIS)|如果希望使用 IIS 来承载应用程序，则是必需的。|  
|Windows 进程激活服务 (WAS)|如果希望使用 WAS 来承载应用程序，则是必需的。|  
  
## <a name="see-also"></a>另请参阅  
 [系统要求](../../../docs/framework/wcf/wcf-system-requirements.md)
