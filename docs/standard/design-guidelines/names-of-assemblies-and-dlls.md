---
title: 程序集和 DLL 的名称
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
author: KrzysztofCwalina
ms.openlocfilehash: 8e20d77c20be8dc74723117f3b0910ecc2090ef7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130970"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="9c76d-102">程序集和 DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="9c76d-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="9c76d-103">程序集是托管代码程序的部署和标识单元。</span><span class="sxs-lookup"><span data-stu-id="9c76d-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="9c76d-104">虽然程序集可以跨一个或多个文件，但通常程序集与 DLL 是一对一映射的。</span><span class="sxs-lookup"><span data-stu-id="9c76d-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="9c76d-105">因此，本部分仅描述 DLL 命名约定，然后可以将其映射到程序集命名约定。</span><span class="sxs-lookup"><span data-stu-id="9c76d-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="9c76d-106">**✓ 要** 为程序集 DLL 选择能够使人联想到大量功能的名称，例如 System.Data。</span><span class="sxs-lookup"><span data-stu-id="9c76d-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="9c76d-107">程序集和 DLL 名称不必与命名空间名称相对应，但在命名程序集时应采用命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="9c76d-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="9c76d-108">通常是根据程序集中包含的命名空间的公共前缀来命名 DLL。</span><span class="sxs-lookup"><span data-stu-id="9c76d-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="9c76d-109">例如，如果程序集的两个命名空间为 `MyCompany.MyTechnology.FirstFeature` 和 `MyCompany.MyTechnology.SecondFeature`，则可将其命名为 `MyCompany.MyTechnology.dll`。</span><span class="sxs-lookup"><span data-stu-id="9c76d-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="9c76d-110">**✓ 考虑**按照下面的模式命名 Dll：</span><span class="sxs-lookup"><span data-stu-id="9c76d-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="9c76d-111">其中`<Component>`包含一个或多个以点号分隔的子句。</span><span class="sxs-lookup"><span data-stu-id="9c76d-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="9c76d-112">例如：</span><span class="sxs-lookup"><span data-stu-id="9c76d-112">For example:</span></span>  
  
 <span data-ttu-id="9c76d-113">`Litware.Controls.dll`。</span><span class="sxs-lookup"><span data-stu-id="9c76d-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="9c76d-114">部分 © 2005，2009 Microsoft Corporation。*保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="9c76d-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="9c76d-115">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="9c76d-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9c76d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="9c76d-116">See also</span></span>

- [<span data-ttu-id="9c76d-117">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="9c76d-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="9c76d-118">命名规则</span><span class="sxs-lookup"><span data-stu-id="9c76d-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
