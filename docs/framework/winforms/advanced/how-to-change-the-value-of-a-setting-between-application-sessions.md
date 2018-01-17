---
title: "如何：在应用程序会话之间更改设置值"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c00e61001d9c8877b1fcaa0e938c92249c7915e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>如何：在应用程序会话之间更改设置值
有时，你可能想要更改设置编译应用程序并将其部署之后的应用程序会话之间的值。 例如，你可能想要更改连接字符串以指向正确的数据库的位置。 由于编译应用程序并将其部署之后，设计时工具不可用，则必须更改在该文件中手动设置值。  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>若要更改应用程序会话之间设置的值  
  
1.  使用 Microsoft 记事本或某些其他文本或 XML 编辑器，打开你的应用程序与关联的.config 文件。  
  
2.  找到你想要更改的设置的项。 其外观应类似于下面给出的示例。  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3.  键入你的设置的新值并保存文件。  
  
## <a name="see-also"></a>请参阅  
 [使用应用程序设置和用户设置](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [应用程序设置概述](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
