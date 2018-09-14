---
title: WPF 安全策略 — 安全工程
ms.date: 03/30/2017
helpviewer_keywords:
- security [WPF], testing techniques
- Security Development Lifecycle (SDL), security analysis [WPF]
- Security Development Lifecycle (SDL), threat modeling
- Security Development Lifecycle (SDL), testing techniques
- Security Development Lifecycle (SDL), source analysis tools
- Security Development Lifecycle (SDL), critical code management
- threat modeling [WPF]
ms.assetid: 0fc04394-4e47-49ca-b0cf-8cd1161d95b9
ms.openlocfilehash: fd29696d88eba5c1363464334b63cb2ab0df4a0e
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2018
ms.locfileid: "45510242"
---
# <a name="wpf-security-strategy---security-engineering"></a><span data-ttu-id="cab68-102">WPF 安全策略 - 安全工程</span><span class="sxs-lookup"><span data-stu-id="cab68-102">WPF Security Strategy - Security Engineering</span></span>
<span data-ttu-id="cab68-103">可信计算是 Microsoft 为确保生成安全代码而首创的一项技术。</span><span class="sxs-lookup"><span data-stu-id="cab68-103">Trustworthy Computing is a Microsoft initiative for ensuring the production of secure code.</span></span> <span data-ttu-id="cab68-104">可信计算技术的一个关键元素是 [!INCLUDE[TLA#tla_sdl](../../../includes/tlasharptla-sdl-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="cab68-104">A key element of the Trustworthy Computing initiative is the [!INCLUDE[TLA#tla_sdl](../../../includes/tlasharptla-sdl-md.md)].</span></span> <span data-ttu-id="cab68-105">[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] 是与标准工程过程一同用于简化提交安全代码的工程实践。</span><span class="sxs-lookup"><span data-stu-id="cab68-105">The [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] is an engineering practice that is used in conjunction with standard engineering processes to facilitate the delivery of secure code.</span></span> <span data-ttu-id="cab68-106">[!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] 包含十个阶段，将规范化、可度量性和附加结构的最佳实践结合在一起，包括：</span><span class="sxs-lookup"><span data-stu-id="cab68-106">The [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] consists of ten phases that combine best practices with formalization, measurability, and additional structure, including:</span></span>  
  
-   <span data-ttu-id="cab68-107">安全设计分析</span><span class="sxs-lookup"><span data-stu-id="cab68-107">Security design analysis</span></span>  
  
-   <span data-ttu-id="cab68-108">基于工具的质量检查</span><span class="sxs-lookup"><span data-stu-id="cab68-108">Tool-based quality checks</span></span>  
  
-   <span data-ttu-id="cab68-109">渗透测试</span><span class="sxs-lookup"><span data-stu-id="cab68-109">Penetration testing</span></span>  
  
-   <span data-ttu-id="cab68-110">最终安全评审</span><span class="sxs-lookup"><span data-stu-id="cab68-110">Final security review</span></span>  
  
-   <span data-ttu-id="cab68-111">发布后产品安全管理</span><span class="sxs-lookup"><span data-stu-id="cab68-111">Post release product security management</span></span>  
  
## <a name="wpf-specifics"></a><span data-ttu-id="cab68-112">WPF 详细信息</span><span class="sxs-lookup"><span data-stu-id="cab68-112">WPF Specifics</span></span>  
 <span data-ttu-id="cab68-113">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 工程团队可以应用和扩展 [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)]，该产品组合包括以下主要方面：</span><span class="sxs-lookup"><span data-stu-id="cab68-113">The [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] engineering team both applies and extends the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], the combination of which includes the following key aspects:</span></span>  
  
 [<span data-ttu-id="cab68-114">威胁建模</span><span class="sxs-lookup"><span data-stu-id="cab68-114">Threat Modeling</span></span>](#threat_modeling)  
  
 [<span data-ttu-id="cab68-115">安全分析和编辑工具</span><span class="sxs-lookup"><span data-stu-id="cab68-115">Security Analysis and Editing Tools</span></span>](#tools)  
  
 [<span data-ttu-id="cab68-116">测试技术</span><span class="sxs-lookup"><span data-stu-id="cab68-116">Testing Techniques</span></span>](#techniques)  
  
 [<span data-ttu-id="cab68-117">关键代码管理</span><span class="sxs-lookup"><span data-stu-id="cab68-117">Critical Code Management</span></span>](#critical_code)  
  
<a name="threat_modeling"></a>   
### <a name="threat-modeling"></a><span data-ttu-id="cab68-118">威胁建模</span><span class="sxs-lookup"><span data-stu-id="cab68-118">Threat Modeling</span></span>  
 <span data-ttu-id="cab68-119">威胁建模是 [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)]的核心组件，用于分析系统，以确定潜在的安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="cab68-119">Threat modeling is a core component of the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], and is used to profile a system to determine potential security vulnerabilities.</span></span> <span data-ttu-id="cab68-120">一旦确定漏洞，威胁模型还可以确保采取适当的缓解措施。</span><span class="sxs-lookup"><span data-stu-id="cab68-120">Once the vulnerabilities are identified, threat modeling also ensures that appropriate mitigations are in place.</span></span>  
  
 <span data-ttu-id="cab68-121">我们以一个杂货店为例，说明威胁模型在高级别上所涉及的以下关键步骤：</span><span class="sxs-lookup"><span data-stu-id="cab68-121">At a high level, threat modeling involves the following key steps by using a grocery store as an example:</span></span>  
  
1.  <span data-ttu-id="cab68-122">**确定资产**。</span><span class="sxs-lookup"><span data-stu-id="cab68-122">**Identifying Assets**.</span></span> <span data-ttu-id="cab68-123">杂货店的资产可能包括员工、保险箱、收银机和库存。</span><span class="sxs-lookup"><span data-stu-id="cab68-123">A grocery store's assets might include employees, a safe, cash registers, and inventory.</span></span>  
  
2.  <span data-ttu-id="cab68-124">**枚举入口点**。</span><span class="sxs-lookup"><span data-stu-id="cab68-124">**Enumerating Entry Points**.</span></span> <span data-ttu-id="cab68-125">杂货店的入口点可能包括前门和后门、窗户、装货区和空调设备。</span><span class="sxs-lookup"><span data-stu-id="cab68-125">A grocery store's entry points might include the front and back doors, windows, the loading dock, and air conditioning units.</span></span>  
  
3.  <span data-ttu-id="cab68-126">**使用入口点调查针对资产的攻击**。</span><span class="sxs-lookup"><span data-stu-id="cab68-126">**Investigating Attacks against Assets using Entry Points**.</span></span> <span data-ttu-id="cab68-127">可能进行的攻击包括通过空调入口点来对杂货店的保险箱资产进行攻击；有人可能会将空调设备拆掉，将保险箱通过空调处拉出杂货店。</span><span class="sxs-lookup"><span data-stu-id="cab68-127">One possible attack could target a grocery store's *safe* asset through the *air conditioning* entry point; the air conditioning unit could be unscrewed to allow the safe to be pulled up through it and out of the store.</span></span>  
  
 <span data-ttu-id="cab68-128">威胁建模应用于整个 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]，包含以下各项：</span><span class="sxs-lookup"><span data-stu-id="cab68-128">Threat modeling is applied throughout [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] and includes the following:</span></span>  
  
-   <span data-ttu-id="cab68-129">[!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] 分析器读取文件、将文本映射到相应的对象模型类并创建实际代码的方式。</span><span class="sxs-lookup"><span data-stu-id="cab68-129">How the [!INCLUDE[TLA2#tla_xaml](../../../includes/tla2sharptla-xaml-md.md)] parser reads files, maps text to corresponding object model classes, and creates the actual code.</span></span>  
  
-   <span data-ttu-id="cab68-130">创建窗口句柄 (hWnd) 并通过其发送消息和呈现窗口内容的方式。</span><span class="sxs-lookup"><span data-stu-id="cab68-130">How a window handle (hWnd) is created, sends messages, and is used for rendering the contents of a window.</span></span>  
  
-   <span data-ttu-id="cab68-131">数据绑定获取资源以及与系统交互的方式。</span><span class="sxs-lookup"><span data-stu-id="cab68-131">How data binding obtains resources and interacts with the system.</span></span>  
  
 <span data-ttu-id="cab68-132">这些威胁模型对于在开发过程中确定安全设计需求以及缓解威胁非常重要。</span><span class="sxs-lookup"><span data-stu-id="cab68-132">These threat models are important for identifying security design requirements and threat mitigations during the development process.</span></span>  
  
<a name="tools"></a>   
### <a name="source-analysis-and-editing-tools"></a><span data-ttu-id="cab68-133">源分析和编辑工具</span><span class="sxs-lookup"><span data-stu-id="cab68-133">Source Analysis and Editing Tools</span></span>  
 <span data-ttu-id="cab68-134">除 [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)] 的手动安全代码评审元素外，[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 团队使用多个工具进行源分析和关联编辑，目的是减少安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="cab68-134">In addition to the manual security code review elements of the [!INCLUDE[TLA2#tla_sdl](../../../includes/tla2sharptla-sdl-md.md)], the [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] team uses several tools for source analysis and associated edits to decrease security vulnerabilities.</span></span> <span data-ttu-id="cab68-135">使用了多种源工具，包括以下各项：</span><span class="sxs-lookup"><span data-stu-id="cab68-135">A wide range of source tools are used, and include the following:</span></span>  
  
-   <span data-ttu-id="cab68-136">**FXCop**：查找托管代码中的常见安全问题，包括继承规则、代码访问安全性的使用情况以及安全地与非托管代码交互操作的方式。</span><span class="sxs-lookup"><span data-stu-id="cab68-136">**FXCop**: Finds common security issues in managed code ranging from inheritance rules to code access security usage to how to safely interoperate with unmanaged code.</span></span> <span data-ttu-id="cab68-137">请参阅[FXCop](http://www.gotdotnet.com/team/fxcop/)。</span><span class="sxs-lookup"><span data-stu-id="cab68-137">See [FXCop](http://www.gotdotnet.com/team/fxcop/).</span></span>  
  
-   <span data-ttu-id="cab68-138">**Prefix/Prefast**：查找非托管代码中的安全漏洞和常见安全问题，例如缓冲区溢出、格式字符串问题以及错误检查。</span><span class="sxs-lookup"><span data-stu-id="cab68-138">**Prefix/Prefast**: Finds security vulnerabilities and common security issues in unmanaged code such as buffer overruns, format string issues, and error checking.</span></span>  
  
-   <span data-ttu-id="cab68-139">**已禁止的 API**：搜索源代码，以识别出众所周知的因意外使用而引发安全问题的函数，例如 `strcpy`。</span><span class="sxs-lookup"><span data-stu-id="cab68-139">**Banned APIs**: Searches source code to identify accidental usage of functions that are well-known for causing security issues, such as `strcpy`.</span></span> <span data-ttu-id="cab68-140">一旦识别出这些函数，将用更安全的替代函数来取代它们。</span><span class="sxs-lookup"><span data-stu-id="cab68-140">Once identified, these functions are replaced with alternatives that are more security.</span></span>  
  
<a name="techniques"></a>   
### <a name="testing-techniques"></a><span data-ttu-id="cab68-141">测试技术</span><span class="sxs-lookup"><span data-stu-id="cab68-141">Testing Techniques</span></span>  
 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]<span data-ttu-id="cab68-142"> 使用多种安全测试技术，包括：</span><span class="sxs-lookup"><span data-stu-id="cab68-142"> uses a variety of security testing techniques that include:</span></span>  
  
-   <span data-ttu-id="cab68-143">**白盒测试**：测试人员查看源代码，然后生成攻击测试</span><span class="sxs-lookup"><span data-stu-id="cab68-143">**Whitebox Testing**: Testers view source code, and then build exploit tests</span></span>  
  
-   <span data-ttu-id="cab68-144">**黑盒测试**：测试人员尝试通过检查 API 和功能来查找安全问题，然后尝试对产品进行攻击。</span><span class="sxs-lookup"><span data-stu-id="cab68-144">**Blackbox Testing**: Testers try to find security exploits by examining the API and features, and then try to attack the product.</span></span>  
  
-   <span data-ttu-id="cab68-145">**对来自其他产品的安全问题进行回归测试**：对来自相关产品的相关安全问题进行测试。</span><span class="sxs-lookup"><span data-stu-id="cab68-145">**Regressing Security Issues from other Products**: Where relevant, security issues from related products are tested.</span></span> <span data-ttu-id="cab68-146">例如，对于 [!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)]，已确定出大约六十个安全问题的相关变体，并已对它们在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 上的适用性进行了测试。</span><span class="sxs-lookup"><span data-stu-id="cab68-146">For example, appropriate variants of approximately sixty security issues for [!INCLUDE[TLA2#tla_ie](../../../includes/tla2sharptla-ie-md.md)] have been identified and tried for their applicability to [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)].</span></span>  
  
-   <span data-ttu-id="cab68-147">**借助文件模糊化执行基于工具的渗透测试**：文件模糊化指利用文件读取器多种输入的输入范围。</span><span class="sxs-lookup"><span data-stu-id="cab68-147">**Tools-Based Penetration Testing through File Fuzzing**: File fuzzing is the exploitation of a file reader's input range through a variety of inputs.</span></span> <span data-ttu-id="cab68-148">在 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 中的一个示例，使用此技术的一个示例就是检查图像解码代码的错误。</span><span class="sxs-lookup"><span data-stu-id="cab68-148">One example in [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] where this technique is used is to check for failure in image decoding code.</span></span>  
  
<a name="critical_code"></a>   
### <a name="critical-code-management"></a><span data-ttu-id="cab68-149">关键代码管理</span><span class="sxs-lookup"><span data-stu-id="cab68-149">Critical Code Management</span></span>  
 <span data-ttu-id="cab68-150">有关[!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)]，[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)]利用.NET Framework 支持标记和跟踪可提升特权的安全关键代码生成安全沙盒 (请参阅**安全关键方法**中[WPF安全策略-平台安全性](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md))。</span><span class="sxs-lookup"><span data-stu-id="cab68-150">For [!INCLUDE[TLA#tla_xbap#plural](../../../includes/tlasharptla-xbapsharpplural-md.md)], [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] builds a security sandbox by using .NET Framework support for marking and tracking security-critical code that elevates privileges (see **Security-Critical Methodology** in [WPF Security Strategy - Platform Security](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)).</span></span> <span data-ttu-id="cab68-151">考虑到对安全关键代码有较高的安全质量要求，因此需要对此类代码进行其他级别的源管理控制和安全审核。</span><span class="sxs-lookup"><span data-stu-id="cab68-151">Given the high security quality requirements on security critical code, such code receives an additional level of source management control and security audit.</span></span> <span data-ttu-id="cab68-152">大约有 5% 到 10% 的 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 由安全关键代码组成，这些代码由专门的审核团队进行审核。</span><span class="sxs-lookup"><span data-stu-id="cab68-152">Approximately 5% to 10% of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] consists of security-critical code, which is reviewed by a dedicated reviewing team.</span></span> <span data-ttu-id="cab68-153">通过跟踪安全关键代码和将每个关键实体（即，包含关键代码的方法）映射到其签署状态来对源代码和签入过程进行管理。</span><span class="sxs-lookup"><span data-stu-id="cab68-153">The source code and check-in process is managed by tracking security critical code and mapping each critical entity (i.e. a method that contains critical code) to its sign off state.</span></span> <span data-ttu-id="cab68-154">签署状态包括一个或多个审阅者的姓名。</span><span class="sxs-lookup"><span data-stu-id="cab68-154">The sign off state includes the names of one or more reviewers.</span></span> <span data-ttu-id="cab68-155">[!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 的每个日常版本都将关键代码与前一版本中的该代码进行比较，以检查未经审批的更改。</span><span class="sxs-lookup"><span data-stu-id="cab68-155">Each daily build of [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] compares the critical code to that in previous builds to check for unapproved changes.</span></span> <span data-ttu-id="cab68-156">如果工程师未经审核团队的批准而自行修改关键代码，则将识别并立即修复该代码。</span><span class="sxs-lookup"><span data-stu-id="cab68-156">If an engineer modifies critical code without approval from the reviewing team, it is identified and fixed immediately.</span></span> <span data-ttu-id="cab68-157">通过这一过程，可以对 [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] 沙盒代码应用级别特高的审核并加以维护。</span><span class="sxs-lookup"><span data-stu-id="cab68-157">This process enables the application and maintenance of an especially high level of scrutiny over [!INCLUDE[TLA2#tla_winclient](../../../includes/tla2sharptla-winclient-md.md)] sandbox code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cab68-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="cab68-158">See Also</span></span>  
 [<span data-ttu-id="cab68-159">安全性</span><span class="sxs-lookup"><span data-stu-id="cab68-159">Security</span></span>](../../../docs/framework/wpf/security-wpf.md)  
 [<span data-ttu-id="cab68-160">WPF 部分信任安全</span><span class="sxs-lookup"><span data-stu-id="cab68-160">WPF Partial Trust Security</span></span>](../../../docs/framework/wpf/wpf-partial-trust-security.md)  
 [<span data-ttu-id="cab68-161">WPF 安全策略 - 平台安全性</span><span class="sxs-lookup"><span data-stu-id="cab68-161">WPF Security Strategy - Platform Security</span></span>](../../../docs/framework/wpf/wpf-security-strategy-platform-security.md)  
 [<span data-ttu-id="cab68-162">高信度计算</span><span class="sxs-lookup"><span data-stu-id="cab68-162">Trustworthy Computing</span></span>](https://www.microsoft.com/mscorp/twc/default.mspx)  
 [<span data-ttu-id="cab68-163">应用程序威胁建模</span><span class="sxs-lookup"><span data-stu-id="cab68-163">Application Threat Modeling</span></span>](https://msdn.microsoft.com/security/securecode/threatmodeling/acetm/)  
 [<span data-ttu-id="cab68-164">安全指导原则：.NET Framework 2.0</span><span class="sxs-lookup"><span data-stu-id="cab68-164">Security Guidelines: .NET Framework 2.0</span></span>](https://msdn.microsoft.com/library/default.asp?url=/library/dnpag2/html/PAGGuidelines0003.asp)
