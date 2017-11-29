---
title: "如何：验证应用程序设置"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- validating application settings
- application settings [Windows Forms], Windows Forms
- application settings [Windows Forms], validating
ms.assetid: 9f145ada-4267-436a-aa4c-c4dcffd0afb7
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 309429c2481bad3a8dff4708d9e2ea8a03057a4e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-validate-application-settings"></a><span data-ttu-id="07d66-102">如何：验证应用程序设置</span><span class="sxs-lookup"><span data-stu-id="07d66-102">How to: Validate Application Settings</span></span>
<span data-ttu-id="07d66-103">本主题演示如何在保留应用程序设置前先验证它们。</span><span class="sxs-lookup"><span data-stu-id="07d66-103">This topic demonstrates how to validate application settings before they are persisted.</span></span>  
  
 <span data-ttu-id="07d66-104">由于应用程序设置是强类型设置，因此在一定程度上可以相信用户无法向给定设置分配错误类型的数据。</span><span class="sxs-lookup"><span data-stu-id="07d66-104">Because application settings are strongly typed, you have some confidence that users cannot assign data of an incorrect type to a given setting.</span></span> <span data-ttu-id="07d66-105">但是，用户仍有可能尝试向设置分配超出可接受范围的值，例如，用户提供的出生日期可能是一个将来日期。</span><span class="sxs-lookup"><span data-stu-id="07d66-105">However, a user still may attempt to assign a value to a setting that falls outside of acceptable bounds—for example, supplying a birth date that occurs in the future.</span></span> <span data-ttu-id="07d66-106"><xref:System.Configuration.ApplicationSettingsBase>所有的应用程序设置类的父类公开四个事件，若要启用此类边界检查。</span><span class="sxs-lookup"><span data-stu-id="07d66-106"><xref:System.Configuration.ApplicationSettingsBase>, the parent class of all application settings classes, exposes four events to enable such bounds checking.</span></span> <span data-ttu-id="07d66-107">处理这些事件会将所有验证代码放置在同一位置中，而不是将其分散到整个项目。</span><span class="sxs-lookup"><span data-stu-id="07d66-107">Handling these events puts all of your validation code in a single location, rather than scattering it throughout your project.</span></span>  
  
 <span data-ttu-id="07d66-108">所用事件取决于需要何时验证设置，如下表所述。</span><span class="sxs-lookup"><span data-stu-id="07d66-108">The event you use depends upon when you need to validate your settings, as described in the following table.</span></span>  
  
|<span data-ttu-id="07d66-109">Event</span><span class="sxs-lookup"><span data-stu-id="07d66-109">Event</span></span>|<span data-ttu-id="07d66-110">发生时间和用法</span><span class="sxs-lookup"><span data-stu-id="07d66-110">Occurrence and use</span></span>|  
|-----------|------------------------|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsLoaded>|<span data-ttu-id="07d66-111">初始加载设置属性组后发生。</span><span class="sxs-lookup"><span data-stu-id="07d66-111">Occurs after the initial loading of a settings property group.</span></span><br /><br /> <span data-ttu-id="07d66-112">在应用程序中使用属性组前，使用此事件验证整个属性组的初始值。</span><span class="sxs-lookup"><span data-stu-id="07d66-112">Use this event to validate initial values for the entire property group before they are used within the application.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>|<span data-ttu-id="07d66-113">在更改单个设置属性的值之前发生。</span><span class="sxs-lookup"><span data-stu-id="07d66-113">Occurs before the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="07d66-114">更改单个属性之前，使用此事件验证该属性。</span><span class="sxs-lookup"><span data-stu-id="07d66-114">Use this event to validate a single property before it is changed.</span></span> <span data-ttu-id="07d66-115">它可以向用户提供有关其操作和选择的即时反馈。</span><span class="sxs-lookup"><span data-stu-id="07d66-115">It can provide immediate feedback to users regarding their actions and choices.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.PropertyChanged>|<span data-ttu-id="07d66-116">在更改单个设置属性的值之后发生。</span><span class="sxs-lookup"><span data-stu-id="07d66-116">Occurs after the value of a single settings property is changed.</span></span><br /><br /> <span data-ttu-id="07d66-117">更改单个属性之后，使用此事件验证该属性。</span><span class="sxs-lookup"><span data-stu-id="07d66-117">Use this event to validate a single property after it is changed.</span></span> <span data-ttu-id="07d66-118">除非需要进行长时间的异步验证处理，否则很少将此事件用于验证操作。</span><span class="sxs-lookup"><span data-stu-id="07d66-118">This event is rarely used for validation unless a lengthy, asynchronous validation process is required.</span></span>|  
|<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>|<span data-ttu-id="07d66-119">在存储设置属性组之前发生。</span><span class="sxs-lookup"><span data-stu-id="07d66-119">Occurs before the settings property group is stored.</span></span><br /><br /> <span data-ttu-id="07d66-120">将属性组保留到磁盘之前，使用此事件验证整个属性组的值。</span><span class="sxs-lookup"><span data-stu-id="07d66-120">Use this event to validate values for the entire property group before they are persisted to disk.</span></span>|  
  
 <span data-ttu-id="07d66-121">通常，不会在同一应用程序中使用所有这些事件进行验证操作。</span><span class="sxs-lookup"><span data-stu-id="07d66-121">Typically, you will not use all of these events within the same application for validation purposes.</span></span> <span data-ttu-id="07d66-122">例如，它通常是可以通过仅处理满足所有的验证要求<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>事件。</span><span class="sxs-lookup"><span data-stu-id="07d66-122">For example, it is often possible to fulfill all validation requirements by handling only the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>  
  
 <span data-ttu-id="07d66-123">事件处理程序检测到无效值时通常执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="07d66-123">An event handler generally performs one of the following actions when it detects an invalid value:</span></span>  
  
-   <span data-ttu-id="07d66-124">自动提供已知是正确的值，如默认值。</span><span class="sxs-lookup"><span data-stu-id="07d66-124">Automatically supplies a value known to be correct, such as the default value.</span></span>  
  
-   <span data-ttu-id="07d66-125">再次询问服务器代码用户，以获取信息。</span><span class="sxs-lookup"><span data-stu-id="07d66-125">Re-queries the user of server code for information.</span></span>  
  
-   <span data-ttu-id="07d66-126">对于如及其关联的操作之前引发的事件<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>和<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>，使用<xref:System.ComponentModel.CancelEventArgs>参数来取消该操作。</span><span class="sxs-lookup"><span data-stu-id="07d66-126">For events raised before their associated actions, such as <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> and <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>, uses the <xref:System.ComponentModel.CancelEventArgs> argument to cancel the operation.</span></span>  
  
 <span data-ttu-id="07d66-127">有关事件处理的详细信息，请参阅[事件处理程序概述](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="07d66-127">For more information about event handling, see [Event Handlers Overview](../../../../docs/framework/winforms/event-handlers-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="07d66-128">下面的过程演示如何测试使用的有效的出生日期<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>或<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>事件。</span><span class="sxs-lookup"><span data-stu-id="07d66-128">The following procedures show how to test for a valid birth date using either the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> or the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span> <span data-ttu-id="07d66-129">这些过程是在假定已创建应用程序设置的情况下编写的；在此示例中，我们将对名为 `DateOfBirth` 的设置执行边界检查。</span><span class="sxs-lookup"><span data-stu-id="07d66-129">The procedures were written under the assumption that you have already created your application settings; in this example, we will perform bounds checking on a setting named `DateOfBirth`.</span></span> <span data-ttu-id="07d66-130">有关创建设置的详细信息，请参阅[如何：创建应用程序设置](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="07d66-130">For more information about creating settings, see [How to: Create Application Settings](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md).</span></span>  
  
### <a name="to-obtain-the-application-settings-object"></a><span data-ttu-id="07d66-131">获取应用程序设置对象</span><span class="sxs-lookup"><span data-stu-id="07d66-131">To obtain the application settings object</span></span>  
  
-   <span data-ttu-id="07d66-132">通过完成以下项目符号项之一，获取对应用程序设置对象（包装器实例）的引用：</span><span class="sxs-lookup"><span data-stu-id="07d66-132">Obtain a reference to the application settings object (the wrapper instance) by completing one of the following bulleted items:</span></span>  
  
    -   <span data-ttu-id="07d66-133">如果使用“属性编辑器”中的“Visual Studio 应用程序设置”对话框创建设置，则可通过以下表达式检索为语言生成的默认设置对象。</span><span class="sxs-lookup"><span data-stu-id="07d66-133">If you created your settings using the Visual Studio Application Settings dialog box in the **Property Editor**, you can retrieve the default settings object generated for your language through the following expression.</span></span>  
  
        ```csharp  
        Configuration.Settings.Default   
        ```  
  
        ```vb  
        MySettings.Default   
        ```  
  
         <span data-ttu-id="07d66-134">- 或 -</span><span class="sxs-lookup"><span data-stu-id="07d66-134">-or-</span></span>  
  
    -   <span data-ttu-id="07d66-135">如果是 Visual Basic 开发人员并使用项目设计器创建应用程序设置，则可通过使用 [My.Settings Object](~/docs/visual-basic/language-reference/objects/my-settings-object.md) 对象来检索设置。</span><span class="sxs-lookup"><span data-stu-id="07d66-135">If you are a Visual Basic developer and you created your application settings using the Project Designer, you can retrieve your settings by using the [My.Settings Object](~/docs/visual-basic/language-reference/objects/my-settings-object.md).</span></span>  
  
         <span data-ttu-id="07d66-136">- 或 -</span><span class="sxs-lookup"><span data-stu-id="07d66-136">-or-</span></span>  
  
    -   <span data-ttu-id="07d66-137">如果由派生自创建你的设置<xref:System.Configuration.ApplicationSettingsBase>直接，你需要手动实例化类。</span><span class="sxs-lookup"><span data-stu-id="07d66-137">If you created your settings by deriving from <xref:System.Configuration.ApplicationSettingsBase> directly, you need to instantiate your class manually.</span></span>  
  
        ```csharp  
        MyCustomSettings settings = new MyCustomSettings();  
        ```  
  
        ```vb  
        Dim Settings as New MyCustomSettings()  
        ```  
  
 <span data-ttu-id="07d66-138">下列过程的编写依据：假定应用程序设置对象是通过完成本过程中最后一个项目符号项来获取的。</span><span class="sxs-lookup"><span data-stu-id="07d66-138">The following procedures were written under the assumption that the application settings object was obtained by completing the last bulleted item in this procedure.</span></span>  
  
### <a name="to-validate-application-settings-when-a-setting-is-changing"></a><span data-ttu-id="07d66-139">设置更改时验证应用程序设置</span><span class="sxs-lookup"><span data-stu-id="07d66-139">To validate Application Settings when a setting is changing</span></span>  
  
1.  <span data-ttu-id="07d66-140">如果你是 C# 开发人员，在窗体或控件的`Load`事件，添加事件处理程序<xref:System.Configuration.ApplicationSettingsBase.SettingChanging>事件。</span><span class="sxs-lookup"><span data-stu-id="07d66-140">If you are a C# developer, in your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingChanging> event.</span></span>  
  
     <span data-ttu-id="07d66-141">- 或 -</span><span class="sxs-lookup"><span data-stu-id="07d66-141">-or-</span></span>  
  
     <span data-ttu-id="07d66-142">如果是 Visual Basic 开发人员，则应使用 `WithEvents` 关键字声明 `Settings` 变量。</span><span class="sxs-lookup"><span data-stu-id="07d66-142">If you are a Visual Basic developer, you should declare the `Settings` variable using the `WithEvents` keyword.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingChanging += new SettingChangingEventHandler(MyCustomSettings_SettingChanging);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(sender as Object, e as EventArgs)  
        AddHandler settings.SettingChanging, AddressOf MyCustomSettings_SettingChanging  
    End Sub   
    ```  
  
2.  <span data-ttu-id="07d66-143">定义事件处理程序，并在该事件处理程序中编写代码，以便对出生日期执行边界检查。</span><span class="sxs-lookup"><span data-stu-id="07d66-143">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>  
  
    ```csharp  
    private void MyCustomSettings_SettingChanging(Object sender, SettingChangingEventArgs e)  
    {  
        if (e.SettingName.Equals("DateOfBirth")) {  
            Date newDate = (Date)e.NewValue;  
            If (newDate > Date.Now) {  
                e.Cancel = true;  
                // Inform the user.  
            }  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingChanging(sender as Object, e as SettingChangingEventArgs) Handles Settings.SettingChanging  
        If (e.SettingName.Equals("DateOfBirth")) Then  
            Dim NewDate as Date = CType(e.NewValue, Date)  
            If (NewDate > Date.Now) Then  
                e.Cancel = True  
                ' Inform the user.  
            End If  
        End If  
    End Sub  
    ```  
  
### <a name="to-validate-application-settings-when-a-save-occurs"></a><span data-ttu-id="07d66-144">保存时验证应用程序设置</span><span class="sxs-lookup"><span data-stu-id="07d66-144">To validate Application Settings when a Save occurs</span></span>  
  
1.  <span data-ttu-id="07d66-145">在窗体或控件的`Load`事件，添加事件处理程序<xref:System.Configuration.ApplicationSettingsBase.SettingsSaving>事件。</span><span class="sxs-lookup"><span data-stu-id="07d66-145">In your form or control's `Load` event, add an event handler for the <xref:System.Configuration.ApplicationSettingsBase.SettingsSaving> event.</span></span>  
  
    ```csharp  
    public void Form1_Load(Object sender, EventArgs e)   
    {  
        settings.SettingsSaving += new SettingsSavingEventHandler(MyCustomSettings_SettingsSaving);  
    }  
    ```  
  
    ```vb  
    Public Sub Form1_Load(Sender as Object, e as EventArgs)  
        AddHandler settings.SettingsSaving, AddressOf MyCustomSettings_SettingsSaving  
    End Sub  
    ```  
  
2.  <span data-ttu-id="07d66-146">定义事件处理程序，并在该事件处理程序中编写代码，以便对出生日期执行边界检查。</span><span class="sxs-lookup"><span data-stu-id="07d66-146">Define the event handler, and write the code inside of it to perform bounds checking on the birth date.</span></span>  
  
    ```csharp  
    private void MyCustomSettings_SettingsSaving(Object sender, SettingsSavingEventArgs e)  
    {  
        if (this["DateOfBirth"] > Date.Now) {  
            e.Cancel = true;  
        }  
    }  
    ```  
  
    ```vb  
    Private Sub MyCustomSettings_SettingsSaving(Sender as Object, e as SettingsSavingEventArgs)  
        If (Me["DateOfBirth"] > Date.Now) Then  
            e.Cancel = True  
        End If  
    End Sub  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="07d66-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07d66-147">See Also</span></span>  
 [<span data-ttu-id="07d66-148">在 Windows 窗体中创建事件处理程序</span><span class="sxs-lookup"><span data-stu-id="07d66-148">Creating Event Handlers in Windows Forms</span></span>](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)  
 [<span data-ttu-id="07d66-149">如何：创建应用程序设置</span><span class="sxs-lookup"><span data-stu-id="07d66-149">How to: Create Application Settings</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-application-settings.md)
