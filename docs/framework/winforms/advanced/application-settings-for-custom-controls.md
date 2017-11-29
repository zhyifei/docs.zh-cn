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
# <a name="application-settings-for-custom-controls"></a><span data-ttu-id="abab3-102">自定义控件的应用程序设置</span><span class="sxs-lookup"><span data-stu-id="abab3-102">Application Settings for Custom Controls</span></span>
<span data-ttu-id="abab3-103">你必须完成某些任务，以使保存应用程序设置，当第三方应用程序中承载的控件的功能的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="abab3-103">You must complete certain tasks to give your custom controls the ability to persist application settings when the controls are hosted in third-party applications.</span></span>  
  
 <span data-ttu-id="abab3-104">有关应用程序设置功能的文档的大部分是编写假定表示你正在创建独立的应用程序。</span><span class="sxs-lookup"><span data-stu-id="abab3-104">Most of the documentation about the Application Settings feature is written under the assumption that you are creating a standalone application.</span></span> <span data-ttu-id="abab3-105">但是，如果你在其应用程序中创建其他开发人员将承载的控件，你需要执行一些附加步骤，为您的控件，以便保持其设置正确。</span><span class="sxs-lookup"><span data-stu-id="abab3-105">However, if you are creating a control that other developers will host in their applications, you need to take a few additional steps for your control to persist its settings properly.</span></span>  
  
## <a name="application-settings-and-custom-controls"></a><span data-ttu-id="abab3-106">应用程序设置和自定义控件</span><span class="sxs-lookup"><span data-stu-id="abab3-106">Application Settings and Custom Controls</span></span>  
 <span data-ttu-id="abab3-107">为您能够正确地保持其设置的控件，它必须通过创建其自己专用的应用程序设置包装器类，派生自封装进程<xref:System.Configuration.ApplicationSettingsBase>。</span><span class="sxs-lookup"><span data-stu-id="abab3-107">For your control to properly persist its settings, it must encapsulate the process by creating its own dedicated applications settings wrapper class, derived from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="abab3-108">此外，必须实现的主控件类<xref:System.Configuration.IPersistComponentSettings>。</span><span class="sxs-lookup"><span data-stu-id="abab3-108">Additionally, the main control class must implement the <xref:System.Configuration.IPersistComponentSettings>.</span></span> <span data-ttu-id="abab3-109">该接口包含多个属性，以及两种方法，<xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A>和<xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>。</span><span class="sxs-lookup"><span data-stu-id="abab3-109">The interface contains several properties as well as two methods, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> and <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.</span></span> <span data-ttu-id="abab3-110">如果控件添加到窗体使用**Windows 窗体设计器**在 Visual Studio 中，Windows 窗体将调用<xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A>自动在初始化该控件时; 你必须调用<xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>自己在`Dispose`你的控件的方法。</span><span class="sxs-lookup"><span data-stu-id="abab3-110">If you add your control to a form using the **Windows Forms Designer** in Visual Studio, Windows Forms will call <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatically when the control is initialized; you must call <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> yourself in the `Dispose` method of your control.</span></span>  
  
 <span data-ttu-id="abab3-111">此外，你应为应用程序设置自定义控件，可以在设计时环境，如 Visual Studio 中正常工作的顺序实现以下：</span><span class="sxs-lookup"><span data-stu-id="abab3-111">In addition, you should implement the following in order for application settings for custom controls to work properly in design-time environments such as Visual Studio:</span></span>  
  
1.  <span data-ttu-id="abab3-112">具有一个采用构造函数的自定义应用程序设置类<xref:System.ComponentModel.IComponent>作为单个参数。</span><span class="sxs-lookup"><span data-stu-id="abab3-112">A custom application settings class with a constructor that takes an <xref:System.ComponentModel.IComponent> as a single parameter.</span></span> <span data-ttu-id="abab3-113">使用此类来保存和加载的所有应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="abab3-113">Use this class to save and load all of your application settings.</span></span> <span data-ttu-id="abab3-114">在创建此类的新实例时，将传递自定义控件使用的构造函数。</span><span class="sxs-lookup"><span data-stu-id="abab3-114">When you create a new instance of this class, pass your custom control using the constructor.</span></span>  
  
2.  <span data-ttu-id="abab3-115">创建此自定义设置类，创建控件并将其放置在窗体，如在窗体的后<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="abab3-115">Create this custom settings class after the control has been created and placed on a form, such as in the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
 <span data-ttu-id="abab3-116">有关创建自定义设置类的说明，请参阅[如何： 创建应用程序设置](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="abab3-116">For instructions on creating a custom settings class, see [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).</span></span>  
  
## <a name="settings-keys-and-shared-settings"></a><span data-ttu-id="abab3-117">设置密钥和共享的设置</span><span class="sxs-lookup"><span data-stu-id="abab3-117">Settings Keys and Shared Settings</span></span>  
 <span data-ttu-id="abab3-118">某些控件可以在同一个窗体中多次使用。</span><span class="sxs-lookup"><span data-stu-id="abab3-118">Some controls can be used multiple times within the same form.</span></span> <span data-ttu-id="abab3-119">大多数情况下，你需要这些控件，以保存其自己单独的设置。</span><span class="sxs-lookup"><span data-stu-id="abab3-119">Most of the time, you will want these controls to persist their own individual settings.</span></span> <span data-ttu-id="abab3-120">与<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>属性<xref:System.Configuration.IPersistComponentSettings>，您可以提供一个唯一字符串，以区分窗体上控件的多个版本。</span><span class="sxs-lookup"><span data-stu-id="abab3-120">With the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> property on <xref:System.Configuration.IPersistComponentSettings>, you can supply a unique string that acts to disambiguate multiple versions of a control on a form.</span></span>  
  
 <span data-ttu-id="abab3-121">若要实现的最简单方法<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>是使用<xref:System.Windows.Forms.Control.Name%2A>的控件属性<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="abab3-121">The simplest way to implement <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> is to use the <xref:System.Windows.Forms.Control.Name%2A> property of the control for the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>.</span></span> <span data-ttu-id="abab3-122">当你加载或保存该控件的设置时，您传递的值<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>到<xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>属性<xref:System.Configuration.ApplicationSettingsBase>类。</span><span class="sxs-lookup"><span data-stu-id="abab3-122">When you load or save the control's settings, you pass the value of <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> on to the <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> property of the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span> <span data-ttu-id="abab3-123">它将用户的设置保存到 XML 时，应用程序设置将使用此唯一键。</span><span class="sxs-lookup"><span data-stu-id="abab3-123">Application Settings uses this unique key when it persists the user's settings to XML.</span></span> <span data-ttu-id="abab3-124">下面的代码示例演示如何`<userSettings>`部分可能看起来的一个名为的自定义控件实例`CustomControl1`，以保存的设置其`Text`属性。</span><span class="sxs-lookup"><span data-stu-id="abab3-124">The following code example shows how a `<userSettings>` section may look for an instance of a custom control named `CustomControl1` that saves a setting for its `Text` property.</span></span>  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 <span data-ttu-id="abab3-125">未提供的值的控件的任何实例<xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>将共享相同的设置。</span><span class="sxs-lookup"><span data-stu-id="abab3-125">Any instances of a control that do not supply a value for <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> will share the same settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abab3-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="abab3-126">See Also</span></span>  
 <xref:System.Configuration.ApplicationSettingsBase>  
 <xref:System.Configuration.IPersistComponentSettings>  
 [<span data-ttu-id="abab3-127">应用程序设置体系结构</span><span class="sxs-lookup"><span data-stu-id="abab3-127">Application Settings Architecture</span></span>](../../../../docs/framework/winforms/advanced/application-settings-architecture.md)
