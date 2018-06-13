---
title: WCF 所要求的操作系统资源
ms.date: 03/30/2017
ms.assetid: cdd9a331-53fe-4e0d-bdfe-782264aec5c9
ms.openlocfilehash: 4522f1c59c8f74281a0e197338c6206ab29c229b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33498639"
---
# <a name="operating-system-resources-required-by-wcf"></a>WCF 所要求的操作系统资源
Windows Communication Foundation (WCF) 取决于几个资源，由操作系统正常工作。 下表列出了这些资源。  
  
|资源|描述|  
|--------------|-----------------|  
|Microsoft 分布式事务协调器 (MSDTC)|支持 OleTx 事务所必需。|  
|Internet 信息服务 (IIS)|如果希望使用 IIS 来承载应用程序，则是必需的。|  
|Windows 进程激活服务 (WAS)|如果希望使用 WAS 来承载应用程序，则是必需的。|  
  
## <a name="see-also"></a>请参阅  
 [系统要求](../../../docs/framework/wcf/wcf-system-requirements.md)
