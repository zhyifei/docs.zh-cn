---
title: <Directives>元素 (.NET Native)
ms.date: 03/30/2017
ms.assetid: 444846f3-48d5-4341-a43e-69f7221389eb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9ec9a09e2fc03adbfcff0d7e69489e37da6e4a5
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2019
ms.locfileid: "71049885"
---
# <a name="directives-element-net-native"></a><span data-ttu-id="ec2a7-102">\<指令 > 元素（.NET Native）</span><span class="sxs-lookup"><span data-stu-id="ec2a7-102">\<Directives> Element (.NET Native)</span></span>
<span data-ttu-id="ec2a7-103">.NET Native 的每个运行时指令文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="ec2a7-103">The root element in every runtime directives file for .NET Native.</span></span>  
  
 `<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">` 
  
## <a name="syntax"></a><span data-ttu-id="ec2a7-104">语法</span><span class="sxs-lookup"><span data-stu-id="ec2a7-104">Syntax</span></span>  
  
```xml  
<Directives xmlns="http://schemas.microsoft.com/netfx/2013/01/metadata">  
   <!-- child elements -->   
</Directives>  
```  
  
## <a name="attributes"></a><span data-ttu-id="ec2a7-105">特性</span><span class="sxs-lookup"><span data-stu-id="ec2a7-105">Attributes</span></span>  
  
|<span data-ttu-id="ec2a7-106">特性</span><span class="sxs-lookup"><span data-stu-id="ec2a7-106">Attribute</span></span>|<span data-ttu-id="ec2a7-107">描述</span><span class="sxs-lookup"><span data-stu-id="ec2a7-107">Description</span></span>|  
|---------------|-----------------|  
|`xmlns`|<span data-ttu-id="ec2a7-108">XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="ec2a7-108">The XML namespace.</span></span> <span data-ttu-id="ec2a7-109">其值始终为 **"http://schemas.microsoft.com/netfx/2013/01/metadata"** 。</span><span class="sxs-lookup"><span data-stu-id="ec2a7-109">Its value is always **"http://schemas.microsoft.com/netfx/2013/01/metadata"**.</span></span>|  
  
## <a name="child-elements"></a><span data-ttu-id="ec2a7-110">子元素</span><span class="sxs-lookup"><span data-stu-id="ec2a7-110">Child elements</span></span>  
  
|<span data-ttu-id="ec2a7-111">元素</span><span class="sxs-lookup"><span data-stu-id="ec2a7-111">Element</span></span>|<span data-ttu-id="ec2a7-112">描述</span><span class="sxs-lookup"><span data-stu-id="ec2a7-112">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="ec2a7-113">\<Application></span><span class="sxs-lookup"><span data-stu-id="ec2a7-113">\<Application></span></span>](application-element-net-native.md)|<span data-ttu-id="ec2a7-114">作为应用程序范围内的类型和其元数据可以用于反射的类型成员的容器而服务。</span><span class="sxs-lookup"><span data-stu-id="ec2a7-114">Serves as a container for application-wide types and type members whose metadata is available for reflection.</span></span>|  
|[<span data-ttu-id="ec2a7-115">\<Library></span><span class="sxs-lookup"><span data-stu-id="ec2a7-115">\<Library></span></span>](library-element-net-native.md)|<span data-ttu-id="ec2a7-116">定义那些子类型和类型成员在运行时间要求元数据的程序集。</span><span class="sxs-lookup"><span data-stu-id="ec2a7-116">Defines the assembly whose child types and type members require metadata at run time.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ec2a7-117">备注</span><span class="sxs-lookup"><span data-stu-id="ec2a7-117">Remarks</span></span>  
 <span data-ttu-id="ec2a7-118">每个运行时指令文件都可以只包含一个 `<Directives>` 元素。</span><span class="sxs-lookup"><span data-stu-id="ec2a7-118">Each runtime directives file can contain only one `<Directives>` element.</span></span>  
  
 <span data-ttu-id="ec2a7-119">`<Directives>` 元素可包含零个或一个 [\<Application>](application-element-net-native.md) 元素，以及零个、一个或多个 [\<Library>](library-element-net-native.md) 元素。</span><span class="sxs-lookup"><span data-stu-id="ec2a7-119">The `<Directives>` element can contain zero or one [\<Application>](application-element-net-native.md) element, and zero, one, or more [\<Library>](library-element-net-native.md) elements.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec2a7-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="ec2a7-120">See also</span></span>

- [<span data-ttu-id="ec2a7-121">运行时指令 (rd.xml) 配置文件参考</span><span class="sxs-lookup"><span data-stu-id="ec2a7-121">Runtime Directives (rd.xml) Configuration File Reference</span></span>](runtime-directives-rd-xml-configuration-file-reference.md)
- [<span data-ttu-id="ec2a7-122">运行时指令元素</span><span class="sxs-lookup"><span data-stu-id="ec2a7-122">Runtime Directive Elements</span></span>](runtime-directive-elements.md)
