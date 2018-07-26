---
title: 命名准则
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], about naming guidelines
- naming guidelines [.NET Framework]
- class library design guidelines [.NET Framework], names
- formatting [.NET Framework], names
- identifiers, class library element names
- names [.NET Framework]
- format naming guidelines [.NET Framework]
ms.assetid: fc076d66-9b5f-42d3-aa65-61d970c794a3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 53ffb641d3e507a937c304725b3c8590d046338e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572965"
---
# <a name="naming-guidelines"></a><span data-ttu-id="6c3a3-102">命名准则</span><span class="sxs-lookup"><span data-stu-id="6c3a3-102">Naming Guidelines</span></span>
<span data-ttu-id="6c3a3-103">以下一致的开发中的 framework 的命名约定集可以是框架的可用性起着主要作用。</span><span class="sxs-lookup"><span data-stu-id="6c3a3-103">Following a consistent set of naming conventions in the development of a framework can be a major contribution to the framework’s usability.</span></span> <span data-ttu-id="6c3a3-104">它使框架可以广泛分隔项目上的许多开发人员使用。</span><span class="sxs-lookup"><span data-stu-id="6c3a3-104">It allows the framework to be used by many developers on widely separated projects.</span></span> <span data-ttu-id="6c3a3-105">窗体的一致性，超出的框架元素名称必须能轻松理解，必须传达每个元素的功能。</span><span class="sxs-lookup"><span data-stu-id="6c3a3-105">Beyond consistency of form, names of framework elements must be easily understood and must convey the function of each element.</span></span>  
  
 <span data-ttu-id="6c3a3-106">本文的目的是提供一组一致的命名约定，用于生成便于开发人员理解和使用的名称。</span><span class="sxs-lookup"><span data-stu-id="6c3a3-106">The goal of this chapter is to provide a consistent set of naming conventions that results in names that make immediate sense to developers.</span></span>  
  
 <span data-ttu-id="6c3a3-107">尽管采用这些命名约定，因为常规的代码开发指导原则会导致更一致的方式命名在整个代码，将要求你仅将其应用到公共公开的 Api (公共或受保护的类型和成员，并显式实现接口）。</span><span class="sxs-lookup"><span data-stu-id="6c3a3-107">Although adopting these naming conventions as general code development guidelines would result in more consistent naming throughout your code, you are required only to apply them to APIs that are publicly exposed (public or protected types and members, and explicitly implemented interfaces).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6c3a3-108">本节内容</span><span class="sxs-lookup"><span data-stu-id="6c3a3-108">In This Section</span></span>  
 [<span data-ttu-id="6c3a3-109">大小写约定</span><span class="sxs-lookup"><span data-stu-id="6c3a3-109">Capitalization Conventions</span></span>](../../../docs/standard/design-guidelines/capitalization-conventions.md)  
 [<span data-ttu-id="6c3a3-110">通用命名约定</span><span class="sxs-lookup"><span data-stu-id="6c3a3-110">General Naming Conventions</span></span>](../../../docs/standard/design-guidelines/general-naming-conventions.md)  
 [<span data-ttu-id="6c3a3-111">程序集和 DLL 的名称</span><span class="sxs-lookup"><span data-stu-id="6c3a3-111">Names of Assemblies and DLLs</span></span>](../../../docs/standard/design-guidelines/names-of-assemblies-and-dlls.md)  
 [<span data-ttu-id="6c3a3-112">命名空间的名称</span><span class="sxs-lookup"><span data-stu-id="6c3a3-112">Names of Namespaces</span></span>](../../../docs/standard/design-guidelines/names-of-namespaces.md)  
 [<span data-ttu-id="6c3a3-113">类、结构和接口的名称</span><span class="sxs-lookup"><span data-stu-id="6c3a3-113">Names of Classes, Structs, and Interfaces</span></span>](../../../docs/standard/design-guidelines/names-of-classes-structs-and-interfaces.md)  
 [<span data-ttu-id="6c3a3-114">类型成员的名称</span><span class="sxs-lookup"><span data-stu-id="6c3a3-114">Names of Type Members</span></span>](../../../docs/standard/design-guidelines/names-of-type-members.md)  
 [<span data-ttu-id="6c3a3-115">命名参数</span><span class="sxs-lookup"><span data-stu-id="6c3a3-115">Naming Parameters</span></span>](../../../docs/standard/design-guidelines/naming-parameters.md)  
 [<span data-ttu-id="6c3a3-116">命名资源</span><span class="sxs-lookup"><span data-stu-id="6c3a3-116">Naming Resources</span></span>](../../../docs/standard/design-guidelines/naming-resources.md)  
 <span data-ttu-id="6c3a3-117">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="6c3a3-117">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="6c3a3-118">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="6c3a3-118">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c3a3-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="6c3a3-119">See Also</span></span>  
 [<span data-ttu-id="6c3a3-120">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="6c3a3-120">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
