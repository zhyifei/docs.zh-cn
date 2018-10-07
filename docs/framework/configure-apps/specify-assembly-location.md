---
title: 指定程序集&#39;的位置
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [.NET Framework], applications
- application configuration [.NET Framework]
- assemblies [.NET Framework], specifying location
ms.assetid: 1cb92bd7-6bab-44cf-8fd3-36303ce84fea
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 8fedec60b6152e77d6f99bf55cf11ec909fa8f80
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2018
ms.locfileid: "48848044"
---
# <a name="specifying-an-assembly39s-location"></a><span data-ttu-id="cc825-102">指定程序集&#39;的位置</span><span class="sxs-lookup"><span data-stu-id="cc825-102">Specifying an Assembly&#39;s Location</span></span>
<span data-ttu-id="cc825-103">有两种方法来指定程序集的位置：</span><span class="sxs-lookup"><span data-stu-id="cc825-103">There are two ways to specify an assembly's location:</span></span>  
  
-   <span data-ttu-id="cc825-104">使用[ \<b a s e >](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="cc825-104">Using the [\<codeBase>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) element.</span></span>  
  
-   <span data-ttu-id="cc825-105">使用[\<探测 >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="cc825-105">Using the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element.</span></span>  
  
 <span data-ttu-id="cc825-106">此外可以使用[.NET Framework 配置工具 (Mscorcfg.msc)](https://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764)来指定程序集的位置或指定公共语言运行时来探测程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="cc825-106">You can also use the [.NET Framework Configuration Tool (Mscorcfg.msc)](https://msdn.microsoft.com/library/a7106c52-68da-490e-b129-971b2c743764) to specify assembly locations or specify locations for the common language runtime to probe for assemblies.</span></span>  
  
## <a name="using-the-codebase-element"></a><span data-ttu-id="cc825-107">使用\<b a s e > 元素</span><span class="sxs-lookup"><span data-stu-id="cc825-107">Using the \<codeBase> Element</span></span>  
 <span data-ttu-id="cc825-108">可以使用 **\<b a s e >** 只能机配置或发布服务器策略在文件中还将程序集版本重定向的元素。</span><span class="sxs-lookup"><span data-stu-id="cc825-108">You can use the **\<codeBase>** element only in machine configuration or publisher policy files that also redirect the assembly version.</span></span> <span data-ttu-id="cc825-109">当运行时确定要使用的程序集版本时，则会应用确定版本的文件的基本代码设置。</span><span class="sxs-lookup"><span data-stu-id="cc825-109">When the runtime determines which assembly version to use, it applies the code base setting from the file that determines the version.</span></span> <span data-ttu-id="cc825-110">如果指示没有基本代码，运行时探测程序集以正常方式。</span><span class="sxs-lookup"><span data-stu-id="cc825-110">If no code base is indicated, the runtime probes for the assembly in the normal way.</span></span> <span data-ttu-id="cc825-111">有关详细信息，请参阅[运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="cc825-111">For details, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="cc825-112">下面的示例演示如何指定程序集的位置。</span><span class="sxs-lookup"><span data-stu-id="cc825-112">The following example shows how to specify an assembly's location.</span></span>  
  
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
  
 <span data-ttu-id="cc825-113">**版本**属性是必需的所有强名称的程序集，但不是具有强名称的程序集，应省略。</span><span class="sxs-lookup"><span data-stu-id="cc825-113">The **version** attribute is required for all strong-named assemblies but should be omitted for assemblies that are not strong-named.</span></span> <span data-ttu-id="cc825-114">**\<B a s e >** 元素需要**href**属性。</span><span class="sxs-lookup"><span data-stu-id="cc825-114">The **\<codeBase>** element requires the **href** attribute.</span></span> <span data-ttu-id="cc825-115">不能指定版本范围 **\<b a s e >** 元素。</span><span class="sxs-lookup"><span data-stu-id="cc825-115">You cannot specify version ranges in the **\<codeBase>** element.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc825-116">如果你所提供的不是强名称的程序集的基本代码的提示，提示必须指向应用程序基控件或应用程序基目录的子目录。</span><span class="sxs-lookup"><span data-stu-id="cc825-116">If you are supplying a code base hint for an assembly that is not strong-named, the hint must point to the application base or a subdirectory of the application base directory.</span></span>  
  
## <a name="using-the-probing-element"></a><span data-ttu-id="cc825-117">使用\<探测 > 元素</span><span class="sxs-lookup"><span data-stu-id="cc825-117">Using the \<probing> Element</span></span>  
 <span data-ttu-id="cc825-118">运行时定位程序集不具有通过探测的基本代码。</span><span class="sxs-lookup"><span data-stu-id="cc825-118">The runtime locates assemblies that do not have a code base by probing.</span></span> <span data-ttu-id="cc825-119">探测的详细信息，请参阅[运行时如何定位程序集](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="cc825-119">For more information about probing, see [How the Runtime Locates Assemblies](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).</span></span>  
  
 <span data-ttu-id="cc825-120">可以使用[\<探测 >](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md)应用程序配置文件来指定运行时查找程序集时应搜索的子目录中的元素。</span><span class="sxs-lookup"><span data-stu-id="cc825-120">You can use the [\<probing>](../../../docs/framework/configure-apps/file-schema/runtime/probing-element.md) element in the application configuration file to specify subdirectories the runtime should search when locating an assembly.</span></span> <span data-ttu-id="cc825-121">下面的示例演示如何指定运行时应搜索的目录。</span><span class="sxs-lookup"><span data-stu-id="cc825-121">The following example shows how to specify directories the runtime should search.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
         <probing privatePath="bin;bin2\subbin;bin3"/>  
      </assemblyBinding>  
   </runtime>  
</configuration>  
```  
  
 <span data-ttu-id="cc825-122">**PrivatePath**属性包含运行时应搜索程序集的目录。</span><span class="sxs-lookup"><span data-stu-id="cc825-122">The **privatePath** attribute contains the directories that the runtime should search for assemblies.</span></span> <span data-ttu-id="cc825-123">如果应用程序位于 C:\Program Files\MyApp，运行时将查找 C:\Program Files\MyApp\Bin、 C:\Program Files\MyApp\Bin2\Subbin 和 C:\Program Files\MyApp\Bin3 中未指定基本代码的程序集。</span><span class="sxs-lookup"><span data-stu-id="cc825-123">If the application is located at C:\Program Files\MyApp, the runtime will look for assemblies that do not specify a code base in C:\Program Files\MyApp\Bin, C:\Program Files\MyApp\Bin2\Subbin, and C:\Program Files\MyApp\Bin3.</span></span> <span data-ttu-id="cc825-124">中指定的目录**privatePath**必须是应用程序基目录的子目录。</span><span class="sxs-lookup"><span data-stu-id="cc825-124">The directories specified in **privatePath** must be subdirectories of the application base directory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc825-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="cc825-125">See Also</span></span>  
 <span data-ttu-id="cc825-126">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)（公共语言运行时中的程序集）</span><span class="sxs-lookup"><span data-stu-id="cc825-126">[Assemblies in the Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)</span></span>  
 [<span data-ttu-id="cc825-127">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="cc825-127">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)  
 [<span data-ttu-id="cc825-128">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="cc825-128">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 [<span data-ttu-id="cc825-129">配置.NET Framework 应用</span><span class="sxs-lookup"><span data-stu-id="cc825-129">Configuring .NET Framework Apps</span></span>](https://msdn.microsoft.com/library/d789b592-fcb5-4e3d-8ac9-e0299adaaa42)
