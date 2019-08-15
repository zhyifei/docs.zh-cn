---
title: 如何：向应用程序添加多组设置 (C#)
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: c6842d11c04e905d42734af939f2c3f0cfeacd47
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040128"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>如何：将多组设置添加到应用程序中的 C\#

在某些情况下, 你可能希望在应用程序中包含多组设置。 例如, 如果你正在开发一个应用程序, 其中一组特定的设置需要频繁更改, 则可能会将它们全部隔开到一个文件中, 以便可以将该文件替换为批发, 而不影响其他设置。 Visual Studio 允许你向项目添加多个设置集。 可以通过`Properties.Settings`对象访问其他设置集。

## <a name="add-an-additional-set-of-settings"></a>添加一组其他设置

1. 在 Visual Studio 的 "**项目**" 菜单中, 选择 "**添加新项**"。

   此时将打开“添加新项”对话框。

2. 在 "**添加新项**" 对话框中, 选择 "**设置文件**", 输入文件的名称, 然后单击 "**添加**" 以将新的设置文件添加到解决方案。

3. 在**解决方案资源管理器**中, 将新的设置文件拖到**Properties**文件夹中。 这允许您的新设置在代码中可用。

4. 像添加任何其他设置文件一样, 在此文件中添加和使用设置。 可以通过`Properties.Settings`对象访问这组设置。

## <a name="see-also"></a>请参阅

- [使用应用程序设置和用户设置](using-application-settings-and-user-settings.md)
- [应用程序设置概述](application-settings-overview.md)
