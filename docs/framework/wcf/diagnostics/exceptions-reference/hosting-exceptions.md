---
title: 承载异常
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: f2bc7d0ca09faa2598990437295d1abf0cff3c45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934727"
---
# <a name="hosting-exceptions"></a>承载异常
本主题列出了由承载生成的所有异常。  
  
## <a name="exception-list"></a>异常列表  
  
|资源代码|资源字符串|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|不允许完整的 URI。 对于 ServiceHostingEnvironment.EnsureServiceAvailable API，不允许完整的 URI。 对相应的服务使用虚拟路径。|  
|Hosting_BuildProviderCouldNotCreateType|在服务编译期间，无法加载指定的 CLR 类型。 验证此类型，或者定义位于应用程序的源代码文件中的\\包含在已编译的程序集中位于应用程序的 \App_Code 目录\\\bin 目录，或位于中安装的程序集全局程序集缓存。 类型名区分大小写。 目录，例如\\\App_Code 和\\\bin 必须位于应用程序的根目录中。 \\\App_Code 和\\\bin 目录不能嵌套在子目录中。|
