---
title: 如何：在运行时读取设置 (C#)
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 6a40718d57fad4041eeea2fded03b7256abbe8d1
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710224"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>如何：在运行时读取设置 C\#

可以通过“属性”对象在运行时读取应用程序范围和用户范围的设置。 Properties 对象通过在其上定义的项目的默认命名空间中的 "Properties" 属性公开项目的所有默认设置。  
  
## <a name="to-read-settings-at-run-time-with-c"></a>在运行时通过 C 读取设置\#
  
请通过 Properties.Settings.Default 成员访问相应的设置。 下面的示例演示如何将名为 `myColor` 的设置分配给 BackColor 属性。 这要求你在之前已创建包含名为 `myColor` 的设置（其类型为 `System.Drawing.Color`）的设置文件。 有关创建设置文件的信息, 请参阅[如何:在设计时](how-to-create-a-new-setting-at-design-time.md)创建新设置。  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>请参阅

- [使用应用程序设置和用户设置](using-application-settings-and-user-settings.md)
- [如何：在运行时编写用户设置C#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [应用程序设置概述](application-settings-overview.md)
