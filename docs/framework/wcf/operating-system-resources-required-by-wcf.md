---
title: WCF 所要求的操作系统资源
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: ac9bd5ed7c2092720c6521d0f78185c3fbf9f94b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318948"
---
# <a name="operating-system-resources-required-by-wcf"></a>WCF 所要求的操作系统资源
Windows Communication Foundation （WCF）依赖于操作系统提供的多个资源才能正常运行。 下表列出了这些资源。  
  
|资源|描述|  
|--------------|-----------------|  
|Microsoft 分布式事务协调器 (MSDTC)|支持 OleTx 事务所必需。|  
|Internet Information Services (IIS)|如果希望使用 IIS 来承载应用程序，则是必需的。|  
|Windows 进程激活服务 (WAS)|如果希望使用 WAS 来承载应用程序，则是必需的。|  
  
## <a name="see-also"></a>请参阅

- [系统要求](wcf-system-requirements.md)
