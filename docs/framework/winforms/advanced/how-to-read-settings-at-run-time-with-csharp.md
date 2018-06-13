---
title: 如何：在运行时读取设置 (C#)
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8259e2f429718793c01868855651d1000620fae5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521009"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>如何：在运行时读取设置 (C#) #
可以通过“属性”对象在运行时读取应用程序范围和用户范围的设置。 “属性”对象通过 Properties.Settings.Default 成员公开项目的所有默认设置。  
  
### <a name="to-read-settings-at-run-time-with-c"></a>在运行时读取设置 (C#)  
  
-   请通过 Properties.Settings.Default 成员访问相应的设置。 下面的示例演示如何将名为 `myColor` 的设置分配给 BackColor 属性。 这要求你在之前已创建包含名为 `myColor` 的设置（其类型为 `System.Drawing.Color`）的设置文件。 有关创建设置文件的信息，请参阅[How To： 在设计时创建新的设置](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md)。  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a>请参阅  
 [使用应用程序设置和用户设置](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [如何：在运行时使用 C# 编写用户设置](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
 [应用程序设置概述](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
