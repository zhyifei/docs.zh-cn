---
title: 创建自定义日志侦听器 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- custom log listeners
- My.Application.Log object, custom log listeners
ms.assetid: 0e019115-4b25-4820-afb1-af8c6e391698
ms.openlocfilehash: 07c13d22235f1198188d26122c137db1d91e64e8
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59342437"
---
# <a name="walkthrough-creating-custom-log-listeners-visual-basic"></a><span data-ttu-id="4e8f5-102">演练：创建自定义日志侦听器 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e8f5-102">Walkthrough: Creating Custom Log Listeners (Visual Basic)</span></span>
<span data-ttu-id="4e8f5-103">本演练演示如何创建自定义日志侦听器，并将其配置为侦听 `My.Application.Log` 对象的输出。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-103">This walkthrough demonstrates how to create a custom log listener and configure it to listen to the output of the `My.Application.Log` object.</span></span>  
  
## <a name="getting-started"></a><span data-ttu-id="4e8f5-104">入门</span><span class="sxs-lookup"><span data-stu-id="4e8f5-104">Getting Started</span></span>  
 <span data-ttu-id="4e8f5-105">日志侦听器必须继承自 <xref:System.Diagnostics.TraceListener> 类。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-105">Log listeners must inherit from the <xref:System.Diagnostics.TraceListener> class.</span></span>  
  
#### <a name="to-create-the-listener"></a><span data-ttu-id="4e8f5-106">创建侦听器</span><span class="sxs-lookup"><span data-stu-id="4e8f5-106">To create the listener</span></span>  
  
-   <span data-ttu-id="4e8f5-107">在应用程序中，创建继承自 <xref:System.Diagnostics.TraceListener> 的类，其名称为 `SimpleListener`。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-107">In your application, create a class named `SimpleListener` that inherits from <xref:System.Diagnostics.TraceListener>.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#16)]  
  
     <span data-ttu-id="4e8f5-108">基类所需的 <xref:System.Diagnostics.TraceListener.Write%2A> 和 <xref:System.Diagnostics.TraceListener.WriteLine%2A> 方法调用 `MsgBox`，以显示其输入。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-108">The <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods, required by the base class, call `MsgBox` to display their input.</span></span>  
  
     <span data-ttu-id="4e8f5-109"><xref:System.Security.Permissions.HostProtectionAttribute> 特性应用于 <xref:System.Diagnostics.TraceListener.Write%2A> 和 <xref:System.Diagnostics.TraceListener.WriteLine%2A> 方法，使其特性与基类方法匹配。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-109">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is applied to the <xref:System.Diagnostics.TraceListener.Write%2A> and <xref:System.Diagnostics.TraceListener.WriteLine%2A> methods so that their attributes match the base class methods.</span></span> <span data-ttu-id="4e8f5-110"><xref:System.Security.Permissions.HostProtectionAttribute> 特性使运行代码的主机能够确定代码会公开主机保护同步。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-110">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute allows the host that runs the code to determine that the code exposes host-protection synchronization.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4e8f5-111"><xref:System.Security.Permissions.HostProtectionAttribute> 特性仅在可托管公共语言运行时且实现主机保护的非托管应用程序上有效，如 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-111">The <xref:System.Security.Permissions.HostProtectionAttribute> attribute is effective only on unmanaged applications that host the common language runtime and that implement host protection, such as SQL Server.</span></span>  
  
 <span data-ttu-id="4e8f5-112">若要确保 `My.Application.Log` 使用日志侦听器，应对包含日志侦听器的程序集执行强名称。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-112">To ensure that `My.Application.Log` uses your log listener, you should strongly name the assembly that contains your log listener.</span></span>  
  
 <span data-ttu-id="4e8f5-113">接下来的过程提供一些用于创建强名称日志侦听器程序集的简单步骤。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-113">The next procedure provides some simple steps for creating a strongly named log-listener assembly.</span></span> <span data-ttu-id="4e8f5-114">有关详细信息，请参阅[创建和使用具有强名称的程序集](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-114">For more information, see [Creating and Using Strong-Named Assemblies](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md).</span></span>  
  
#### <a name="to-strongly-name-the-log-listener-assembly"></a><span data-ttu-id="4e8f5-115">对日志侦听器程序集执行强名称</span><span class="sxs-lookup"><span data-stu-id="4e8f5-115">To strongly name the log-listener assembly</span></span>  
  
1. <span data-ttu-id="4e8f5-116">在 **“解决方案资源管理器”** 中选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-116">Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="4e8f5-117">在 **“项目”** 菜单上，选择 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-117">On the **Project** menu, choose **Properties**.</span></span>   
  
2. <span data-ttu-id="4e8f5-118">单击“签名”选项卡。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-118">Click the **Signing** tab.</span></span>  
  
3. <span data-ttu-id="4e8f5-119">选择“为程序集签名”框。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-119">Select the **Sign the assembly** box.</span></span>  
  
4. <span data-ttu-id="4e8f5-120">在“选择强名称密钥文件”下拉列表中，选择“\<新建>”。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-120">Select **\<New>** from the **Choose a strong name key file** drop-down list.</span></span>  
  
     <span data-ttu-id="4e8f5-121">将打开“创建强名称密钥”对话框。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-121">The **Create Strong Name Key** dialog box opens.</span></span>  
  
5. <span data-ttu-id="4e8f5-122">在“密钥文件名”框中提供密钥文件的名称。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-122">Provide a name for the key file in the **Key file name** box.</span></span>  
  
6. <span data-ttu-id="4e8f5-123">在“输入密码”和“确认密码”框中输入密码。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-123">Enter a password in the **Enter password** and **Confirm password** boxes.</span></span>  
  
7. <span data-ttu-id="4e8f5-124">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-124">Click **OK**.</span></span>  
  
8. <span data-ttu-id="4e8f5-125">重新生成应用程序。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-125">Rebuild the application.</span></span>  
  
## <a name="adding-the-listener"></a><span data-ttu-id="4e8f5-126">添加侦听器</span><span class="sxs-lookup"><span data-stu-id="4e8f5-126">Adding the Listener</span></span>  
 <span data-ttu-id="4e8f5-127">现在程序集已具有强名称，需要确定侦听器的强名称，以便 `My.Application.Log` 使用日志侦听器。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-127">Now that the assembly has a strong name, you need to determine the strong name of the listener so that `My.Application.Log` uses your log listener.</span></span>  
  
 <span data-ttu-id="4e8f5-128">强名称类型的格式如下所示。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-128">The format of a strongly named type is as follows.</span></span>  
  
 <span data-ttu-id="4e8f5-129">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span><span class="sxs-lookup"><span data-stu-id="4e8f5-129">\<type name>, \<assembly name>, \<version number>, \<culture>, \<strong name></span></span>  
  
#### <a name="to-determine-the-strong-name-of-the-listener"></a><span data-ttu-id="4e8f5-130">确定侦听器的强名称</span><span class="sxs-lookup"><span data-stu-id="4e8f5-130">To determine the strong name of the listener</span></span>  
  
-   <span data-ttu-id="4e8f5-131">以下代码演示如何确定 `SimpleListener` 的强名称类型名称。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-131">The following code shows how to determine the strongly named type name for `SimpleListener`.</span></span>  
  
     [!code-vb[VbVbalrMyApplicationLog#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyApplicationLog/VB/Form1.vb#17)]  
  
     <span data-ttu-id="4e8f5-132">该类型的强名称取决于项目。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-132">The strong name of the type depends on your project.</span></span>  
  
 <span data-ttu-id="4e8f5-133">借助强名称，可以将侦听器添加到 `My.Application.Log` 日志侦听器集合中。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-133">With the strong name, you can add the listener to the `My.Application.Log` log-listener collection.</span></span>  
  
#### <a name="to-add-the-listener-to-myapplicationlog"></a><span data-ttu-id="4e8f5-134">将侦听器添加到 My.Application.Log</span><span class="sxs-lookup"><span data-stu-id="4e8f5-134">To add the listener to My.Application.Log</span></span>  
  
1. <span data-ttu-id="4e8f5-135">在“解决方案资源管理器”中右键单击 app.config，然后选择“打开”。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-135">Right-click on app.config in the **Solution Explorer** and choose **Open**.</span></span>  
  
     <span data-ttu-id="4e8f5-136">或</span><span class="sxs-lookup"><span data-stu-id="4e8f5-136">-or-</span></span>  
  
     <span data-ttu-id="4e8f5-137">如果其中有 app.config 文件：</span><span class="sxs-lookup"><span data-stu-id="4e8f5-137">If there is an app.config file:</span></span>  
  
    1.  <span data-ttu-id="4e8f5-138">在 **“项目”** 菜单上选择 **“添加新项”**。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-138">On the **Project** menu, choose **Add New Item**.</span></span>  
  
    2.  <span data-ttu-id="4e8f5-139">在“添加新项”  对话框中，选择“应用程序配置文件” 。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-139">From the **Add New Item** dialog box, choose **Application Configuration File**.</span></span>  
  
    3.  <span data-ttu-id="4e8f5-140">单击 **添加**。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-140">Click **Add**.</span></span>  
  
2. <span data-ttu-id="4e8f5-141">找到 `<listeners>` 部分，该部分位于 `<source>` 属性为“DefaultSource”的 `name` 部分当中，后者又位于 `<sources>` 部分之下。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-141">Locate the `<listeners>` section, in the `<source>` section with the `name` attribute "DefaultSource", located in the `<sources>` section.</span></span> <span data-ttu-id="4e8f5-142">`<sources>` 部分位于 `<system.diagnostics>` 部分当中，后者又位于顶级 `<configuration>` 部分之下。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-142">The `<sources>` section is located in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
3. <span data-ttu-id="4e8f5-143">将此元素添加到 `<listeners>` 部分：</span><span class="sxs-lookup"><span data-stu-id="4e8f5-143">Add this element to the `<listeners>` section:</span></span>  
  
    ```xml  
    <add name="SimpleLog" />  
    ```  
  
4. <span data-ttu-id="4e8f5-144">找到 `<sharedListeners>` 部分，该部分位于 `<system.diagnostics>` 部分当中，后者又位于顶级 `<configuration>` 部分之下。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-144">Locate the `<sharedListeners>` section, in the `<system.diagnostics>` section, in the top-level `<configuration>` section.</span></span>  
  
5. <span data-ttu-id="4e8f5-145">将此元素添加到该 `<sharedListeners>` 部分：</span><span class="sxs-lookup"><span data-stu-id="4e8f5-145">Add this element to that `<sharedListeners>` section:</span></span>  
  
    ```xml  
    <add name="SimpleLog" type="SimpleLogStrongName" />  
    ```  
  
     <span data-ttu-id="4e8f5-146">将 `SimpleLogStrongName` 的值更改为该侦听器的强名称。</span><span class="sxs-lookup"><span data-stu-id="4e8f5-146">Change the value of `SimpleLogStrongName` to be the strong name of the listener.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e8f5-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="4e8f5-147">See also</span></span>

- <xref:Microsoft.VisualBasic.Logging.Log?displayProperty=nameWithType>
- [<span data-ttu-id="4e8f5-148">使用应用程序日志</span><span class="sxs-lookup"><span data-stu-id="4e8f5-148">Working with Application Logs</span></span>](../../../../visual-basic/developing-apps/programming/log-info/working-with-application-logs.md)
- [<span data-ttu-id="4e8f5-149">如何：记录异常</span><span class="sxs-lookup"><span data-stu-id="4e8f5-149">How to: Log Exceptions</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-log-exceptions.md)
- [<span data-ttu-id="4e8f5-150">如何：写入日志消息</span><span class="sxs-lookup"><span data-stu-id="4e8f5-150">How to: Write Log Messages</span></span>](../../../../visual-basic/developing-apps/programming/log-info/how-to-write-log-messages.md)
- [<span data-ttu-id="4e8f5-151">演练：更改 My.Application.Log 写入信息的位置</span><span class="sxs-lookup"><span data-stu-id="4e8f5-151">Walkthrough: Changing Where My.Application.Log Writes Information</span></span>](../../../../visual-basic/developing-apps/programming/log-info/walkthrough-changing-where-my-application-log-writes-information.md)
