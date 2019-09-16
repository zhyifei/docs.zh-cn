---
title: 如何：在企业中锁定终结点
ms.date: 03/30/2017
ms.assetid: 1b7eaab7-da60-4cf7-9d6a-ec02709cf75d
ms.openlocfilehash: fb9232c98f672701c60fa9228bb34d7b24d52330
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796967"
---
# <a name="how-to-lock-down-endpoints-in-the-enterprise"></a><span data-ttu-id="84f20-102">如何：在企业中锁定终结点</span><span class="sxs-lookup"><span data-stu-id="84f20-102">How to: Lock Down Endpoints in the Enterprise</span></span>

<span data-ttu-id="84f20-103">大企业往往要求开发的应用程序符合企业安全策略。</span><span class="sxs-lookup"><span data-stu-id="84f20-103">Large enterprises often require that applications are developed in compliance with enterprise security policies.</span></span> <span data-ttu-id="84f20-104">以下主题讨论如何开发和安装可用于验证计算机上安装的所有 Windows Communication Foundation （WCF）客户端应用程序的客户端终结点验证程序。</span><span class="sxs-lookup"><span data-stu-id="84f20-104">The following topic discusses how to develop and install a client endpoint validator that can be used to validate all Windows Communication Foundation (WCF) client applications installed on computers.</span></span>

<span data-ttu-id="84f20-105">在这种情况下，验证程序是客户端验证程序，因为此终结点行为已添加到 machine.config 文件中的客户端[ \<commonBehaviors >](../../configure-apps/file-schema/wcf/commonbehaviors.md)部分。</span><span class="sxs-lookup"><span data-stu-id="84f20-105">In this case, the validator is a client validator because this endpoint behavior is added to the client [\<commonBehaviors>](../../configure-apps/file-schema/wcf/commonbehaviors.md) section in the machine.config file.</span></span> <span data-ttu-id="84f20-106">WCF 只为客户端应用程序加载常见终结点行为，并仅为服务应用程序加载常见服务行为。</span><span class="sxs-lookup"><span data-stu-id="84f20-106">WCF loads common endpoint behaviors only for client applications and loads common service behaviors only for service applications.</span></span> <span data-ttu-id="84f20-107">若要为服务应用程序安装此相同验证程序，验证程序必须为服务行为。</span><span class="sxs-lookup"><span data-stu-id="84f20-107">To install this same validator for service applications, the validator must be a service behavior.</span></span> <span data-ttu-id="84f20-108">有关详细信息，请参阅[ \<commonBehaviors >](../../configure-apps/file-schema/wcf/commonbehaviors.md)部分。</span><span class="sxs-lookup"><span data-stu-id="84f20-108">For more information, see the [\<commonBehaviors>](../../configure-apps/file-schema/wcf/commonbehaviors.md) section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="84f20-109">当应用程序在部分信任环境中<xref:System.Security.AllowPartiallyTrustedCallersAttribute>运行时，不会运行添加到配置文件的[ \<commonBehaviors >](../../configure-apps/file-schema/wcf/commonbehaviors.md)部分中的属性（APTCA）未标记的服务或终结点行为，且不会运行发生这种情况时，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="84f20-109">Service or endpoint behaviors not marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute (APTCA) that are added to the [\<commonBehaviors>](../../configure-apps/file-schema/wcf/commonbehaviors.md) section of a configuration file are not run when the application runs in a partial trust environment, and no exception is thrown when this occurs.</span></span> <span data-ttu-id="84f20-110">若要强制运行公共行为（如验证程序），必须执行以下任一操作：</span><span class="sxs-lookup"><span data-stu-id="84f20-110">To enforce the running of common behaviors such as validators, you must either:</span></span>
>
> - <span data-ttu-id="84f20-111">使用<xref:System.Security.AllowPartiallyTrustedCallersAttribute>属性标记常见行为，以使其在部署为部分信任应用程序时能够运行。</span><span class="sxs-lookup"><span data-stu-id="84f20-111">Mark your common behavior with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute so that it can run when deployed as a Partial Trust application.</span></span> <span data-ttu-id="84f20-112">请注意，可以在计算机上设置注册表项，以防运行标有 APTCA 的程序集。</span><span class="sxs-lookup"><span data-stu-id="84f20-112">Note that a registry entry can be set on the computer to prevent APTCA-marked assemblies from running..</span></span>
>
> - <span data-ttu-id="84f20-113">确保将应用程序部署为完全受信任的应用程序，用户不能修改代码访问安全设置以在部分信任环境中运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="84f20-113">Ensure that if the application is deployed as a fully-trusted application that users cannot modify the code-access security settings to run the application in a Partial Trust environment.</span></span> <span data-ttu-id="84f20-114">如果用户可以这样做，则自定义验证程序不会运行，且不引发任何异常。</span><span class="sxs-lookup"><span data-stu-id="84f20-114">If they can do so, the custom validator does not run and no exception is thrown.</span></span> <span data-ttu-id="84f20-115">若要确保这一点，请参阅使用`levelfinal` [代码访问安全策略工具（caspol.exe）](https://go.microsoft.com/fwlink/?LinkId=248222)的选项。</span><span class="sxs-lookup"><span data-stu-id="84f20-115">For one way to ensure this, see the `levelfinal` option using [Code Access Security Policy Tool (Caspol.exe)](https://go.microsoft.com/fwlink/?LinkId=248222).</span></span>
>
> <span data-ttu-id="84f20-116">有关详细信息，请参阅[部分信任的最佳实践](../feature-details/partial-trust-best-practices.md)和[支持的部署方案](../feature-details/supported-deployment-scenarios.md)。</span><span class="sxs-lookup"><span data-stu-id="84f20-116">For more information, see [Partial Trust Best Practices](../feature-details/partial-trust-best-practices.md) and [Supported Deployment Scenarios](../feature-details/supported-deployment-scenarios.md).</span></span>

### <a name="to-create-the-endpoint-validator"></a><span data-ttu-id="84f20-117">创建终结点验证程序</span><span class="sxs-lookup"><span data-stu-id="84f20-117">To create the endpoint validator</span></span>

1. <span data-ttu-id="84f20-118">使用 <xref:System.ServiceModel.Description.IEndpointBehavior> 方法中所需的验证步骤创建一个 <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A>。</span><span class="sxs-lookup"><span data-stu-id="84f20-118">Create an <xref:System.ServiceModel.Description.IEndpointBehavior> with the desired validation steps in the <xref:System.ServiceModel.Description.IEndpointBehavior.Validate%2A> method.</span></span> <span data-ttu-id="84f20-119">下面的代码提供了一个示例。</span><span class="sxs-lookup"><span data-stu-id="84f20-119">The following code provides an example.</span></span> <span data-ttu-id="84f20-120">（`InternetClientValidatorBehavior` 取自[安全验证](../samples/security-validation.md)示例。）</span><span class="sxs-lookup"><span data-stu-id="84f20-120">(The `InternetClientValidatorBehavior` is taken from the [Security Validation](../samples/security-validation.md) sample.)</span></span>

    [!code-csharp[LockdownValidation#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorbehavior.cs#2)]

2. <span data-ttu-id="84f20-121">创建用于注册步骤 1 中创建的终结点验证程序的新 <xref:System.ServiceModel.Configuration.BehaviorExtensionElement>。</span><span class="sxs-lookup"><span data-stu-id="84f20-121">Create new <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> that registers the endpoint validator created in step 1.</span></span> <span data-ttu-id="84f20-122">下面的代码示例演示了此过程。</span><span class="sxs-lookup"><span data-stu-id="84f20-122">The following code example shows this.</span></span> <span data-ttu-id="84f20-123">（此示例的原始代码位于[安全验证](../samples/security-validation.md)示例中。）</span><span class="sxs-lookup"><span data-stu-id="84f20-123">(The original code for this example is in the [Security Validation](../samples/security-validation.md) sample.)</span></span>

    [!code-csharp[LockdownValidation#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/internetclientvalidatorelement.cs#3)]

3. <span data-ttu-id="84f20-124">确保用强名称对编译的程序集签名。</span><span class="sxs-lookup"><span data-stu-id="84f20-124">Make sure the compiled assembly is signed with a strong name.</span></span> <span data-ttu-id="84f20-125">有关详细信息，请参阅[强名称工具（sn.exe）。EXE）](https://go.microsoft.com/fwlink/?LinkId=248217)和编译器命令。</span><span class="sxs-lookup"><span data-stu-id="84f20-125">For details, see the [Strong Name Tool (SN.EXE)](https://go.microsoft.com/fwlink/?LinkId=248217) and the compiler commands for your language.</span></span>

### <a name="to-install-the-validator-into-the-target-computer"></a><span data-ttu-id="84f20-126">将验证程序安装到目标计算机中</span><span class="sxs-lookup"><span data-stu-id="84f20-126">To install the validator into the target computer</span></span>

1. <span data-ttu-id="84f20-127">使用恰当的机制安装终结点验证程序。</span><span class="sxs-lookup"><span data-stu-id="84f20-127">Install the endpoint validator using the appropriate mechanism.</span></span> <span data-ttu-id="84f20-128">在企业中，可以使用组策略和 Systems Management Server (SMS)。</span><span class="sxs-lookup"><span data-stu-id="84f20-128">In an enterprise, this can be using Group Policy and Systems Management Server (SMS).</span></span>

2. <span data-ttu-id="84f20-129">使用[gacutil.exe （全局程序集缓存工具）](../../tools/gacutil-exe-gac-tool.md)将强名称程序集安装到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="84f20-129">Install the strongly-named assembly into the global assembly cache using the [Gacutil.exe (Global Assembly Cache Tool)](../../tools/gacutil-exe-gac-tool.md).</span></span>

3. <span data-ttu-id="84f20-130">使用 <xref:System.Configuration?displayProperty=nameWithType> 命名空间类型执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="84f20-130">Use the <xref:System.Configuration?displayProperty=nameWithType> namespace types to:</span></span>

    1. <span data-ttu-id="84f20-131">使用完全限定的类型名称将扩展添加到[ \<behaviorExtensions >](../../configure-apps/file-schema/wcf/behaviorextensions.md)节，并锁定该元素。</span><span class="sxs-lookup"><span data-stu-id="84f20-131">Add the extension to the [\<behaviorExtensions>](../../configure-apps/file-schema/wcf/behaviorextensions.md) section using a fully-qualified type name and lock the element.</span></span>

         [!code-csharp[LockdownValidation#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#5)]

    2. <span data-ttu-id="84f20-132">将行为元素添加到`EndpointBehaviors` [ \<commonBehaviors >](../../configure-apps/file-schema/wcf/commonbehaviors.md)节的属性中，并锁定该元素。</span><span class="sxs-lookup"><span data-stu-id="84f20-132">Add the behavior element to the `EndpointBehaviors` property of the [\<commonBehaviors>](../../configure-apps/file-schema/wcf/commonbehaviors.md) section and lock the element.</span></span> <span data-ttu-id="84f20-133">（若要在服务上安装验证程序，该验证程序必须是 <xref:System.ServiceModel.Description.IServiceBehavior>，并已添加到 `ServiceBehaviors` 属性。）下面的代码示例演示执行步骤 a.</span><span class="sxs-lookup"><span data-stu-id="84f20-133">(To install the validator on the service, the validator must be an <xref:System.ServiceModel.Description.IServiceBehavior> and added to the `ServiceBehaviors` property.) The following code example shows the proper configuration after steps a.</span></span> <span data-ttu-id="84f20-134">和 b. 之后的适当配置，唯一例外是有没有强名称。</span><span class="sxs-lookup"><span data-stu-id="84f20-134">and b., with the sole exception that there is no strong name.</span></span>

        [!code-csharp[LockdownValidation#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#6)]

    3. <span data-ttu-id="84f20-135">保存 machine.config 文件。</span><span class="sxs-lookup"><span data-stu-id="84f20-135">Save the machine.config file.</span></span> <span data-ttu-id="84f20-136">下面的代码示例执行步骤 3 中的所有任务，但在本地保存已修改的 machine.config 文件的副本。</span><span class="sxs-lookup"><span data-stu-id="84f20-136">The following code example performs all the tasks in step 3 but saves a copy of the modified machine.config file locally.</span></span>

        [!code-csharp[LockdownValidation#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#7)]

## <a name="example"></a><span data-ttu-id="84f20-137">示例</span><span class="sxs-lookup"><span data-stu-id="84f20-137">Example</span></span>

<span data-ttu-id="84f20-138">下面的代码示例演示如何将公共行为添加到 machine.config 文件并将副本保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="84f20-138">The following code example shows how to add a common behavior to the machine.config file and save a copy to the disk.</span></span> <span data-ttu-id="84f20-139">`InternetClientValidatorBehavior`取自[安全验证](../samples/security-validation.md)示例。</span><span class="sxs-lookup"><span data-stu-id="84f20-139">The `InternetClientValidatorBehavior` is taken from the [Security Validation](../samples/security-validation.md) sample.</span></span>

[!code-csharp[LockdownValidation#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/lockdownvalidation/cs/hostapplication.cs#1)]

## <a name="net-framework-security"></a><span data-ttu-id="84f20-140">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="84f20-140">.NET Framework Security</span></span>

<span data-ttu-id="84f20-141">您可能还需要对配置文件元素进行加密。</span><span class="sxs-lookup"><span data-stu-id="84f20-141">You may also want to encrypt the configuration file elements.</span></span> <span data-ttu-id="84f20-142">有关更多信息，请参见“另请参见”部分。</span><span class="sxs-lookup"><span data-stu-id="84f20-142">For more information, see the See Also section.</span></span>

## <a name="see-also"></a><span data-ttu-id="84f20-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="84f20-143">See also</span></span>

- [<span data-ttu-id="84f20-144">使用 DPAPI 对配置文件元素进行加密</span><span class="sxs-lookup"><span data-stu-id="84f20-144">Encrypting configuration file elements using DPAPI</span></span>](https://go.microsoft.com/fwlink/?LinkId=94954)
- [<span data-ttu-id="84f20-145">使用 RSA 对配置文件元素进行加密</span><span class="sxs-lookup"><span data-stu-id="84f20-145">Encrypting configuration file elements using RSA</span></span>](https://go.microsoft.com/fwlink/?LinkId=94955)
