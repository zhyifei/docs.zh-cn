---
title: 自定义控件的应用程序设置
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], application settings
- application settings [Windows Forms], custom controls
ms.assetid: f44afb74-76cc-44f2-890a-44b7cdc211a1
ms.openlocfilehash: d12caf9ed2cb80d837080badab436b2e9b0b3728
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57714341"
---
# <a name="application-settings-for-custom-controls"></a><span data-ttu-id="b2120-102">自定义控件的应用程序设置</span><span class="sxs-lookup"><span data-stu-id="b2120-102">Application Settings for Custom Controls</span></span>
<span data-ttu-id="b2120-103">必须完成某些任务，以使能够保持应用程序设置时的控件都承载在第三方应用程序中的自定义控件。</span><span class="sxs-lookup"><span data-stu-id="b2120-103">You must complete certain tasks to give your custom controls the ability to persist application settings when the controls are hosted in third-party applications.</span></span>  
  
 <span data-ttu-id="b2120-104">表示正在创建独立的应用程序假设下编写大部分的应用程序设置功能有关的文档。</span><span class="sxs-lookup"><span data-stu-id="b2120-104">Most of the documentation about the Application Settings feature is written under the assumption that you are creating a standalone application.</span></span> <span data-ttu-id="b2120-105">但是，如果要在其应用程序中创建其他开发人员将承载的控件，您需要执行几个额外的步骤为您的控件保存其设置正确。</span><span class="sxs-lookup"><span data-stu-id="b2120-105">However, if you are creating a control that other developers will host in their applications, you need to take a few additional steps for your control to persist its settings properly.</span></span>  
  
## <a name="application-settings-and-custom-controls"></a><span data-ttu-id="b2120-106">应用程序设置和自定义控件</span><span class="sxs-lookup"><span data-stu-id="b2120-106">Application Settings and Custom Controls</span></span>  
 <span data-ttu-id="b2120-107">为能够正确地保持其设置控件，它必须通过创建自己专用的应用程序设置包装类，派生自封装过程<xref:System.Configuration.ApplicationSettingsBase>。</span><span class="sxs-lookup"><span data-stu-id="b2120-107">For your control to properly persist its settings, it must encapsulate the process by creating its own dedicated applications settings wrapper class, derived from <xref:System.Configuration.ApplicationSettingsBase>.</span></span> <span data-ttu-id="b2120-108">此外，主控件类必须实现<xref:System.Configuration.IPersistComponentSettings>。</span><span class="sxs-lookup"><span data-stu-id="b2120-108">Additionally, the main control class must implement the <xref:System.Configuration.IPersistComponentSettings>.</span></span> <span data-ttu-id="b2120-109">此接口包含多个属性，以及两个方法，<xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A>和<xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>。</span><span class="sxs-lookup"><span data-stu-id="b2120-109">The interface contains several properties as well as two methods, <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> and <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>.</span></span> <span data-ttu-id="b2120-110">如果将控件添加到窗体使用**Windows 窗体设计器**在 Visual Studio 中，将调用 Windows 窗体<xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A>自动在初始化该控件时，必须调用<xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A>您在`Dispose`控件的方法。</span><span class="sxs-lookup"><span data-stu-id="b2120-110">If you add your control to a form using the **Windows Forms Designer** in Visual Studio, Windows Forms will call <xref:System.Configuration.IPersistComponentSettings.LoadComponentSettings%2A> automatically when the control is initialized; you must call <xref:System.Configuration.IPersistComponentSettings.SaveComponentSettings%2A> yourself in the `Dispose` method of your control.</span></span>  
  
 <span data-ttu-id="b2120-111">此外，应为应用程序设置以便在设计时环境，如 Visual Studio 中正常工作的自定义控件来实现以下：</span><span class="sxs-lookup"><span data-stu-id="b2120-111">In addition, you should implement the following in order for application settings for custom controls to work properly in design-time environments such as Visual Studio:</span></span>  
  
1.  <span data-ttu-id="b2120-112">具有采用的构造函数的自定义应用程序设置类<xref:System.ComponentModel.IComponent>作为单个参数。</span><span class="sxs-lookup"><span data-stu-id="b2120-112">A custom application settings class with a constructor that takes an <xref:System.ComponentModel.IComponent> as a single parameter.</span></span> <span data-ttu-id="b2120-113">使用此类来保存和加载的所有应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="b2120-113">Use this class to save and load all of your application settings.</span></span> <span data-ttu-id="b2120-114">当创建此类的新实例时，请传递自定义控件使用的构造函数。</span><span class="sxs-lookup"><span data-stu-id="b2120-114">When you create a new instance of this class, pass your custom control using the constructor.</span></span>  
  
2.  <span data-ttu-id="b2120-115">创建控件并将其放置在窗体，如在窗体的后创建此自定义设置类<xref:System.Windows.Forms.Form.Load>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b2120-115">Create this custom settings class after the control has been created and placed on a form, such as in the form's <xref:System.Windows.Forms.Form.Load> event handler.</span></span>  
  
 <span data-ttu-id="b2120-116">有关创建自定义设置类的说明，请参阅[如何：创建应用程序设置](how-to-create-application-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="b2120-116">For instructions on creating a custom settings class, see [How to: Create Application Settings](how-to-create-application-settings.md).</span></span>  
  
## <a name="settings-keys-and-shared-settings"></a><span data-ttu-id="b2120-117">设置密钥和共享的设置</span><span class="sxs-lookup"><span data-stu-id="b2120-117">Settings Keys and Shared Settings</span></span>  
 <span data-ttu-id="b2120-118">某些控件可以在同一个窗体中多次使用。</span><span class="sxs-lookup"><span data-stu-id="b2120-118">Some controls can be used multiple times within the same form.</span></span> <span data-ttu-id="b2120-119">大多数情况下，将需要这些控件，以持久保存其自己单独的设置。</span><span class="sxs-lookup"><span data-stu-id="b2120-119">Most of the time, you will want these controls to persist their own individual settings.</span></span> <span data-ttu-id="b2120-120">与<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>属性上的<xref:System.Configuration.IPersistComponentSettings>，可以提供以区分多个版本的窗体上控件的唯一字符串。</span><span class="sxs-lookup"><span data-stu-id="b2120-120">With the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> property on <xref:System.Configuration.IPersistComponentSettings>, you can supply a unique string that acts to disambiguate multiple versions of a control on a form.</span></span>  
  
 <span data-ttu-id="b2120-121">最简单的方法实现<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>是使用<xref:System.Windows.Forms.Control.Name%2A>的控件属性<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>。</span><span class="sxs-lookup"><span data-stu-id="b2120-121">The simplest way to implement <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> is to use the <xref:System.Windows.Forms.Control.Name%2A> property of the control for the <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>.</span></span> <span data-ttu-id="b2120-122">当加载或保存控件的设置时，您传递的值<xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A>到<xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>属性的<xref:System.Configuration.ApplicationSettingsBase>类。</span><span class="sxs-lookup"><span data-stu-id="b2120-122">When you load or save the control's settings, you pass the value of <xref:System.Configuration.IPersistComponentSettings.SettingsKey%2A> on to the <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> property of the <xref:System.Configuration.ApplicationSettingsBase> class.</span></span> <span data-ttu-id="b2120-123">它将用户的设置保存到 XML 时，应用程序设置将使用此唯一键。</span><span class="sxs-lookup"><span data-stu-id="b2120-123">Application Settings uses this unique key when it persists the user's settings to XML.</span></span> <span data-ttu-id="b2120-124">下面的代码示例演示如何`<userSettings>`部分中的名为的自定义控件的实例可能看起来`CustomControl1`，它将保存的设置其`Text`属性。</span><span class="sxs-lookup"><span data-stu-id="b2120-124">The following code example shows how a `<userSettings>` section may look for an instance of a custom control named `CustomControl1` that saves a setting for its `Text` property.</span></span>  
  
```xml  
<userSettings>  
    <CustomControl1>  
        <setting name="Text" serializedAs="string">  
            <value>Hello, World</value>  
        </setting>  
    </CustomControl1>  
</userSettings>  
```  
  
 <span data-ttu-id="b2120-125">未提供的值的控件的任何实例<xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A>将共享相同的设置。</span><span class="sxs-lookup"><span data-stu-id="b2120-125">Any instances of a control that do not supply a value for <xref:System.Configuration.ApplicationSettingsBase.SettingsKey%2A> will share the same settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2120-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2120-126">See also</span></span>
- <xref:System.Configuration.ApplicationSettingsBase>
- <xref:System.Configuration.IPersistComponentSettings>
- [<span data-ttu-id="b2120-127">应用程序设置体系结构</span><span class="sxs-lookup"><span data-stu-id="b2120-127">Application Settings Architecture</span></span>](application-settings-architecture.md)
