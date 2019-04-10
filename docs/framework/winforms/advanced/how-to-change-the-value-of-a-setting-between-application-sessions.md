---
title: 如何：在应用程序会话间更改设置的值
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], changing
- application settings [Windows Forms], between application sessions
ms.assetid: 1a85911f-97b2-476c-930b-83379edd890c
ms.openlocfilehash: 95e613cb280813cd75d887d3cf147d7c897bc2e6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59318880"
---
# <a name="how-to-change-the-value-of-a-setting-between-application-sessions"></a>如何：在应用程序会话间更改设置的值
有时，你可能想要更改设置后编译和部署应用程序的应用程序会话之间的值。 例如，你可能想要更改连接字符串以指向正确的数据库的位置。 由于编译和部署应用程序后，设计时工具不可用，则必须更改文件中手动设置值。  
  
### <a name="to-change-the-value-of-a-setting-between-application-sessions"></a>若要更改应用程序会话之间设置的值  
  
1. 使用 Microsoft 记事本或一些其他文本或 XML 编辑器，打开你的应用程序与关联的.config 文件。  
  
2. 找到你想要更改的设置的条目。 它应类似于下面显示的示例。  
  
    ```xml  
    <setting name="Setting1" serializeAs="String" >  
       <value>My Setting Value</value>  
    </setting>  
    ```  
  
3. 键入您的设置的新值并保存文件。  
  
## <a name="see-also"></a>请参阅

- [使用应用程序设置和用户设置](using-application-settings-and-user-settings.md)
- [应用程序设置概述](application-settings-overview.md)
