---
title: 指定程序集的位置
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
ms.openlocfilehash: ead69d1e850050214c15295134c06ff6f66e9760
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2020
ms.locfileid: "81646033"
---
# <a name="specifying-an-assemblys-location"></a><span data-ttu-id="c7cf5-102">指定程序集的位置</span><span class="sxs-lookup"><span data-stu-id="c7cf5-102">Specifying an Assembly's Location</span></span>
<span data-ttu-id="c7cf5-103">有两种方法可以指定程序集的位置：</span><span class="sxs-lookup"><span data-stu-id="c7cf5-103">There are two ways to specify an assembly's location:</span></span>  
  
- <span data-ttu-id="c7cf5-104">使用[\<代码库>](./file-schema/runtime/codebase-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-104">Using the [\<codeBase>](./file-schema/runtime/codebase-element.md) element.</span></span>  
  
- <span data-ttu-id="c7cf5-105">使用[\<探测>](./file-schema/runtime/probing-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-105">Using the [\<probing>](./file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="c7cf5-106">您还可以使用[.NET 框架配置工具 （Mscorcfg.msc）](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100))指定程序集位置或指定要探测程序集的通用语言运行时的位置。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/2bc0cxhc(v=vs.100)) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="c7cf5-107">使用\<代码库>元素</span><span class="sxs-lookup"><span data-stu-id="c7cf5-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="c7cf5-108">只能在计算机配置或发布者策略文件中使用**\<codeBase>** 元素，这些文件也会重定向程序集版本。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="c7cf5-109">当运行时确定要使用的程序集版本时，它将从确定版本的文件中应用代码库设置。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="c7cf5-110">如果未指示代码库，则以正常方式探测程序集的运行时探测。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="c7cf5-111">有关详细信息，请参阅[运行时如何查找程序集](../deployment/how-the-runtime-locates-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-111">For details, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="c7cf5-112">下面的示例演示如何指定程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-112">The following example shows how to specify an assembly's location.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
       <dependentAssembly>  
         <assemblyIdentity name="myAssembly"  
                           publicKeyToken="32ab4ba45e0a69a1"  
                           culture="en-us" />  
         <codeBase version="2.0.0.0"  
                   href="http://www.litwareinc.com/myAssembly.dll"/>  
       </dependentAssembly>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="c7cf5-113">所有强命名程序集都需要**版本**属性，但对于未强命名的程序集，应省略版本属性。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="c7cf5-114">**\<代码库>** 元素需要**href**属性。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="c7cf5-115">不能在**\<代码库>** 元素中指定版本范围。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c7cf5-116">如果要为未强命名的程序集提供代码基提示，则提示必须指向应用程序基或应用程序基目录的子目录。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="c7cf5-117">使用\<探测>元素</span><span class="sxs-lookup"><span data-stu-id="c7cf5-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="c7cf5-118">运行时通过探测查找没有代码库的程序集。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="c7cf5-119">有关探测的详细信息，请参阅[运行时如何查找程序集](../deployment/how-the-runtime-locates-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-119">For more information about probing, see [How the Runtime Locates Assemblies](../deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="c7cf5-120">可以使用应用程序配置文件中的[\<探测>](./file-schema/runtime/probing-element.md)元素来指定运行时在定位程序集时应搜索的子目录。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-120">You can use the [\<probing>](./file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="c7cf5-121">下面的示例演示如何指定运行时应搜索的目录。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="c7cf5-122">**专用 Path**属性包含运行时应搜索程序集的目录。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="c7cf5-123">如果应用程序位于 C：_程序文件\MyApp，运行时将查找未在 C：\*程序文件_MyApp_Bin、C：程序文件\MyApp_Subbin 和 C：程序文件\MyApp_Bin3中指定代码库的程序集。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="c7cf5-124">**在私有路径**中指定的目录必须是应用程序基础目录的子目录。</span><span class="sxs-lookup"><span data-stu-id="c7cf5-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7cf5-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c7cf5-125">See also</span></span>

- [<span data-ttu-id="c7cf5-126">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="c7cf5-126">Assemblies in .NET</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="c7cf5-127">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="c7cf5-127">Programming with Assemblies</span></span>](../../standard/assembly/index.md)
- [<span data-ttu-id="c7cf5-128">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="c7cf5-128">How the Runtime Locates Assemblies</span></span>](../deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="c7cf5-129">使用配置文件配置应用</span><span class="sxs-lookup"><span data-stu-id="c7cf5-129">Configuring Apps by using Configuration Files</span></span>](index.md)
