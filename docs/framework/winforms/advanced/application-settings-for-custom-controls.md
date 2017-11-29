---
title: "自定义控件的应用程序设置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3f8292ac459a2943376229ef62466b0a772430dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="application-settings-for-custom-controls"></a>自定义控件的应用程序设置
你必须完成某些任务，以使保存应用程序设置，当第三方应用程序中承载的控件的功能的自定义控件。  
  
 有关应用程序设置功能的文档的大部分是编写假定表示你正在创建独立的应用程序。 但是，如果你在其应用程序中创建其他开发人员将承载的控件，你需要执行一些附加步骤，为您的控件，以便保持其设置正确。  
  
## <a name="application-settings-and-custom-controls"></a>应用程序设置和自定义控件  
 为您能够正确地保持其设置的控件，它必须通过创建其自己专用的应用程序设置包装器类，派生自封装进程<xref:System.Configuration.ApplicationSettingsBase>。 此外，必须实现的主控件类<xref:System.Configuration.IPersistComponentSettings>。 该接口包含多个属性，以及两种方法，<xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A>和<xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>。 如果控件添加到窗体使用**Windows 窗体设计器**在 Visual Studio 中，Windows 窗体将调用<xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A>自动在初始化该控件时; 你必须调用<xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>自己在`Dispose`你的控件的方法。  
  
 此外，你应为应用程序设置自定义控件，可以在设计时环境，如 Visual Studio 中正常工作的顺序实现以下：  
  
1.  具有一个采用构造函数的自定义应用程序设置类<xref:System.ComponentModel.IComponent>作为单个参数。 使用此类来保存和加载的所有应用程序设置。 在创建此类的新实例时，将传递自定义控件使用的构造函数。  
  
2.  创建此自定义设置类，创建控件并将其放置在窗体，如在窗体的后<xref:System.Windows.Forms.Form.Load>事件处理程序。  
  
 有关创建自定义设置类的说明，请参阅[如何： 创建应用程序设置](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)。  
  
## <a name="settings-keys-and-shared-settings"></a>设置密钥和共享的设置  
 某些控件可以在同一个窗体中多次使用。 大多数情况下，你需要这些控件，以保存其自己单独的设置。 与<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>属性<xref:System.Configuration.IPersistComponentSettings>，您可以提供一个唯一字符串，以区分窗体上控件的多个版本。  
  
 若要实现的最简单方法<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>是使用<xref:System.Windows.Forms.Control.Name%2A>的控件属性<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>。 当你加载或保存该控件的设置时，您传递的值<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>到<xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>属性<xref:System.Configuration.ApplicationSettingsBase>类。 它将用户的设置保存到 XML 时，应用程序设置将使用此唯一键。 下面的代码示例演示如何`<userSettings>`部分可能看起来的一个名为的自定义控件实例`CustomControl1`，以保存的设置其`Text`属性。  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 未提供的值的控件的任何实例<xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>将共享相同的设置。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.IPersistComponentSettings>  
 [应用程序设置体系结构](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)
