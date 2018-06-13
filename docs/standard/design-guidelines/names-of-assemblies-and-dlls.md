---
title: 程序集和 DLL 的名称
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c6cf175472d68e99598dd56e170bee3d37ae3c2a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570403"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="d811f-102">程序集和 DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="d811f-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="d811f-103">程序集是部署和托管的代码程序的标识的单元。</span><span class="sxs-lookup"><span data-stu-id="d811f-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="d811f-104">程序集可以跨一个或多个文件，尽管通常程序集进行一对一映射 DLL。</span><span class="sxs-lookup"><span data-stu-id="d811f-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="d811f-105">因此，本部分介绍了唯一 DLL 命名约定，然后可以映射到程序集命名约定。</span><span class="sxs-lookup"><span data-stu-id="d811f-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="d811f-106">**✓ 执行**选择您的程序集建议的功能，例如 System.Data 大量的 Dll 的名称。</span><span class="sxs-lookup"><span data-stu-id="d811f-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="d811f-107">程序集和 DLL 名称无需对应于命名空间名称，但它是合理命名程序集时应遵循的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="d811f-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="d811f-108">好的经验法则是名称的公共前缀的程序集中包含的命名空间所基于的 DLL。</span><span class="sxs-lookup"><span data-stu-id="d811f-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="d811f-109">例如，包含两个命名空间中的程序集`MyCompany.MyTechnology.FirstFeature`和`MyCompany.MyTechnology.SecondFeature`，无法调用`MyCompany.MyTechnology.dll`。</span><span class="sxs-lookup"><span data-stu-id="d811f-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="d811f-110">**请考虑 ✓**按照下面的模式命名 Dll:</span><span class="sxs-lookup"><span data-stu-id="d811f-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="d811f-111">其中`<Component>`包含一个或多个以点分隔的子句。</span><span class="sxs-lookup"><span data-stu-id="d811f-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="d811f-112">例如：</span><span class="sxs-lookup"><span data-stu-id="d811f-112">For example:</span></span>  
  
 <span data-ttu-id="d811f-113">`Litware.Controls.dll`。</span><span class="sxs-lookup"><span data-stu-id="d811f-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="d811f-114">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="d811f-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="d811f-115">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="d811f-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d811f-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="d811f-116">See Also</span></span>  
 [<span data-ttu-id="d811f-117">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="d811f-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="d811f-118">命名规则</span><span class="sxs-lookup"><span data-stu-id="d811f-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
