---
title: "如何：在设计时创建新设置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e8a05b6f37f7686f18a6200e009aabe7eed5537
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-new-setting-at-design-time"></a>如何：在设计时创建新设置
通过使用设置设计器，可以在设计时创建的新的设置。 设置设计器是一个网格样式接口，允许你创建新的设置，并指定这些设置的属性。 必须指定名称、 值、 类型和作用域为新设置。 创建一个设置后，可在代码中访问。  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a>若要在 C# 中的设计时创建新的设置  
  
1.  在**解决方案资源管理器**，展开**属性**你的项目节点。  
  
2.  双击想要添加新设置的.settings 文件。 此文件的默认名称是 Settings.settings。  
  
3.  在设置设计器中，设置名称、 值、 类型和为你设置的作用域。 每一行表示单个设置。  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a>若要在 Visual Basic 中的设计时创建新的设置  
  
1.  在**解决方案资源管理器**，右键单击你的项目节点，然后选择**属性**。  
  
2.  在**属性**页上，选择**设置**选项卡。  
  
3.  在设置设计器中，设置名称、 值、 类型和为你设置的作用域。 每一行表示单个设置。  
  
## <a name="see-also"></a>另请参阅  
 [使用应用程序设置和用户设置](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [应用程序设置概述](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [如何：在设计时更改现有设置的值](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)
