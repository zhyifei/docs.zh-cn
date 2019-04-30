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
ms.openlocfilehash: 1aeef9e1be6e5fe747f440a8cb7f21095cb22f49
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61945491"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="00b69-102">程序集和 DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="00b69-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="00b69-103">程序集是托管代码程序的部署和标识单元。</span><span class="sxs-lookup"><span data-stu-id="00b69-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="00b69-104">虽然程序集可以跨一个或多个文件，但通常程序集与 DLL 是一对一映射的。</span><span class="sxs-lookup"><span data-stu-id="00b69-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="00b69-105">因此，本部分仅描述 DLL 命名约定，然后可以将其映射到程序集命名约定。</span><span class="sxs-lookup"><span data-stu-id="00b69-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>  
  
 <span data-ttu-id="00b69-106">**✓ 要** 为程序集 DLL 选择能够使人联想到大量功能的名称，例如 System.Data。</span><span class="sxs-lookup"><span data-stu-id="00b69-106">**✓ DO** choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>  
  
 <span data-ttu-id="00b69-107">程序集和 DLL 名称不必与命名空间名称相对应，但在命名程序集时应采用命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="00b69-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="00b69-108">通常是根据程序集中包含的命名空间的公共前缀来命名 DLL。</span><span class="sxs-lookup"><span data-stu-id="00b69-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="00b69-109">例如，如果程序集的两个命名空间为 `MyCompany.MyTechnology.FirstFeature` 和 `MyCompany.MyTechnology.SecondFeature`，则可将其命名为 `MyCompany.MyTechnology.dll`。</span><span class="sxs-lookup"><span data-stu-id="00b69-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>  
  
 <span data-ttu-id="00b69-110">**✓ 考虑**按照下面的模式命名 Dll：</span><span class="sxs-lookup"><span data-stu-id="00b69-110">**✓ CONSIDER** naming DLLs according to the following pattern:</span></span>  
  
 `<Company>.<Component>.dll`  
  
 <span data-ttu-id="00b69-111">其中`<Component>`包含一个或多个以点号分隔的子句。</span><span class="sxs-lookup"><span data-stu-id="00b69-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="00b69-112">例如：</span><span class="sxs-lookup"><span data-stu-id="00b69-112">For example:</span></span>  
  
 <span data-ttu-id="00b69-113">`Litware.Controls.dll`。</span><span class="sxs-lookup"><span data-stu-id="00b69-113">`Litware.Controls.dll`.</span></span>  
  
 <span data-ttu-id="00b69-114">部分 © 2005，2009 Microsoft Corporation。*保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="00b69-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="00b69-115">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="00b69-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00b69-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="00b69-116">See also</span></span>

- [<span data-ttu-id="00b69-117">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="00b69-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="00b69-118">命名规则</span><span class="sxs-lookup"><span data-stu-id="00b69-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
