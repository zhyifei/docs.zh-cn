---
title: 어셈블리 및 DLL의 이름
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- names [.NET Framework], DLLs
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
- DLLs, names
ms.assetid: e800b610-31b4-4949-9c14-cb60e9f254be
ms.openlocfilehash: f3c5997f777c937e9726b271afa0ae6d7a19b37d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744167"
---
# <a name="names-of-assemblies-and-dlls"></a><span data-ttu-id="c5b8a-102">어셈블리 및 DLL의 이름</span><span class="sxs-lookup"><span data-stu-id="c5b8a-102">Names of Assemblies and DLLs</span></span>
<span data-ttu-id="c5b8a-103">程序集是托管代码程序的部署和标识单元。</span><span class="sxs-lookup"><span data-stu-id="c5b8a-103">An assembly is the unit of deployment and identity for managed code programs.</span></span> <span data-ttu-id="c5b8a-104">虽然程序集可以跨一个或多个文件，但通常程序集与 DLL 是一对一映射的。</span><span class="sxs-lookup"><span data-stu-id="c5b8a-104">Although assemblies can span one or more files, typically an assembly maps one-to-one with a DLL.</span></span> <span data-ttu-id="c5b8a-105">因此，本部分仅描述 DLL 命名约定，然后可以将其映射到程序集命名约定。</span><span class="sxs-lookup"><span data-stu-id="c5b8a-105">Therefore, this section describes only DLL naming conventions, which then can be mapped to assembly naming conventions.</span></span>

 <span data-ttu-id="c5b8a-106">✔️为程序集 Dll 选择名称，这些名称建议了大块功能，如 System.object。</span><span class="sxs-lookup"><span data-stu-id="c5b8a-106">✔️ DO choose names for your assembly DLLs that suggest large chunks of functionality, such as System.Data.</span></span>

 <span data-ttu-id="c5b8a-107">程序集和 DLL 名称不必与命名空间名称相对应，但在命名程序集时应采用命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="c5b8a-107">Assembly and DLL names don’t have to correspond to namespace names, but it is reasonable to follow the namespace name when naming assemblies.</span></span> <span data-ttu-id="c5b8a-108">通常是根据程序集中包含的命名空间的公共前缀来命名 DLL。</span><span class="sxs-lookup"><span data-stu-id="c5b8a-108">A good rule of thumb is to name the DLL based on the common prefix of the namespaces contained in the assembly.</span></span> <span data-ttu-id="c5b8a-109">例如，如果程序集的两个命名空间为 `MyCompany.MyTechnology.FirstFeature` 和 `MyCompany.MyTechnology.SecondFeature`，则可将其命名为 `MyCompany.MyTechnology.dll`。</span><span class="sxs-lookup"><span data-stu-id="c5b8a-109">For example, an assembly with two namespaces, `MyCompany.MyTechnology.FirstFeature` and `MyCompany.MyTechnology.SecondFeature`, could be called `MyCompany.MyTechnology.dll`.</span></span>

 <span data-ttu-id="c5b8a-110">✔️考虑根据以下模式命名 Dll：</span><span class="sxs-lookup"><span data-stu-id="c5b8a-110">✔️ CONSIDER naming DLLs according to the following pattern:</span></span>

 `<Company>.<Component>.dll`

 <span data-ttu-id="c5b8a-111">其中 `<Component>` 包含一个或多个以句点分隔的子句。</span><span class="sxs-lookup"><span data-stu-id="c5b8a-111">where `<Component>` contains one or more dot-separated clauses.</span></span> <span data-ttu-id="c5b8a-112">예를 들면 다음과 같습니다.:</span><span class="sxs-lookup"><span data-stu-id="c5b8a-112">For example:</span></span>

 <span data-ttu-id="c5b8a-113">`Litware.Controls.dll`.</span><span class="sxs-lookup"><span data-stu-id="c5b8a-113">`Litware.Controls.dll`.</span></span>

 <span data-ttu-id="c5b8a-114">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="c5b8a-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="c5b8a-115">*Pearson Education, Inc의 동의로 재인쇄. 출처: [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 작성자: Krzysztof Cwalina 및 Brad Abrams, 출판 정보: Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span><span class="sxs-lookup"><span data-stu-id="c5b8a-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="c5b8a-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5b8a-116">See also</span></span>

- [<span data-ttu-id="c5b8a-117">프레임워크 디자인 지침</span><span class="sxs-lookup"><span data-stu-id="c5b8a-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="c5b8a-118">명명 지침</span><span class="sxs-lookup"><span data-stu-id="c5b8a-118">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
