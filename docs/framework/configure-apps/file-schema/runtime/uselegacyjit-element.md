---
title: <useLegacyJit> 元素
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3b783a82b1ef964de308532ef544bbfab2397400
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70252227"
---
# <a name="uselegacyjit-element"></a><span data-ttu-id="26dc2-102">\<useLegacyJit> 元素</span><span class="sxs-lookup"><span data-stu-id="26dc2-102">\<useLegacyJit> Element</span></span>

<span data-ttu-id="26dc2-103">确定公共语言运行时是否使用实时编译的旧版 64 位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="26dc2-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="26dc2-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="26dc2-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="26dc2-105">&nbsp;&nbsp;[ **\<运行时 >** ](runtime-element.md)</span><span class="sxs-lookup"><span data-stu-id="26dc2-105">&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)</span></span>\
<span data-ttu-id="26dc2-106">&nbsp;&nbsp;&nbsp;&nbsp; **\<useLegacyJit>**</span><span class="sxs-lookup"><span data-stu-id="26dc2-106">&nbsp;&nbsp;&nbsp;&nbsp;**\<useLegacyJit>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26dc2-107">语法</span><span class="sxs-lookup"><span data-stu-id="26dc2-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="26dc2-108">元素名称`useLegacyJit`区分大小写。</span><span class="sxs-lookup"><span data-stu-id="26dc2-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26dc2-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="26dc2-109">Attributes and elements</span></span>

<span data-ttu-id="26dc2-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="26dc2-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26dc2-111">特性</span><span class="sxs-lookup"><span data-stu-id="26dc2-111">Attributes</span></span>  
  
| <span data-ttu-id="26dc2-112">特性</span><span class="sxs-lookup"><span data-stu-id="26dc2-112">Attribute</span></span> | <span data-ttu-id="26dc2-113">描述</span><span class="sxs-lookup"><span data-stu-id="26dc2-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="26dc2-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="26dc2-114">Required attribute.</span></span><br><br><span data-ttu-id="26dc2-115">指定运行时是否使用旧版64位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="26dc2-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="26dc2-116">enabled 属性</span><span class="sxs-lookup"><span data-stu-id="26dc2-116">enabled attribute</span></span>  
  
| <span data-ttu-id="26dc2-117">值</span><span class="sxs-lookup"><span data-stu-id="26dc2-117">Value</span></span> | <span data-ttu-id="26dc2-118">Description</span><span class="sxs-lookup"><span data-stu-id="26dc2-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="26dc2-119">0</span><span class="sxs-lookup"><span data-stu-id="26dc2-119">0</span></span>     | <span data-ttu-id="26dc2-120">公共语言运行时使用 .NET Framework 4.6 及更高版本中包含的新64位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="26dc2-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="26dc2-121">1</span><span class="sxs-lookup"><span data-stu-id="26dc2-121">1</span></span>     | <span data-ttu-id="26dc2-122">公共语言运行时使用较旧的64位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="26dc2-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="26dc2-123">子元素</span><span class="sxs-lookup"><span data-stu-id="26dc2-123">Child elements</span></span>

<span data-ttu-id="26dc2-124">无</span><span class="sxs-lookup"><span data-stu-id="26dc2-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="26dc2-125">父元素</span><span class="sxs-lookup"><span data-stu-id="26dc2-125">Parent elements</span></span>  
  
| <span data-ttu-id="26dc2-126">元素</span><span class="sxs-lookup"><span data-stu-id="26dc2-126">Element</span></span>         | <span data-ttu-id="26dc2-127">描述</span><span class="sxs-lookup"><span data-stu-id="26dc2-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="26dc2-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="26dc2-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="26dc2-129">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="26dc2-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="26dc2-130">备注</span><span class="sxs-lookup"><span data-stu-id="26dc2-130">Remarks</span></span>  

<span data-ttu-id="26dc2-131">从 .NET Framework 4.6 开始，默认情况下，公共语言运行时为实时（JIT）编译使用新的64位编译器。</span><span class="sxs-lookup"><span data-stu-id="26dc2-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="26dc2-132">在某些情况下，这可能会导致应用程序代码的行为与以前版本的64位 JIT 编译器进行 JIT 编译的行为不同。</span><span class="sxs-lookup"><span data-stu-id="26dc2-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="26dc2-133">通过将`<useLegacyJit>`元素`enabled`的属性设置为`1`，可以禁用新的64位 jit 编译器，而使用旧的64位 jit 编译器编译应用程序。</span><span class="sxs-lookup"><span data-stu-id="26dc2-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="26dc2-134">`<useLegacyJit>`元素仅影响64位 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="26dc2-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="26dc2-135">与32位 JIT 编译器的编译不受影响。</span><span class="sxs-lookup"><span data-stu-id="26dc2-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="26dc2-136">您可以通过两种其他方法启用旧版64位 JIT 编译器，而不是使用配置文件设置：</span><span class="sxs-lookup"><span data-stu-id="26dc2-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="26dc2-137">设置环境变量</span><span class="sxs-lookup"><span data-stu-id="26dc2-137">Setting an environment variable</span></span>

  <span data-ttu-id="26dc2-138">将环境变量设置`0`为（使用新的64位 jit 编译器）或`1` （使用较旧的64位 jit 编译器）： `COMPLUS_useLegacyJit`</span><span class="sxs-lookup"><span data-stu-id="26dc2-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="26dc2-139">环境变量具有*全局作用域*，这意味着它会影响计算机上运行的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="26dc2-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="26dc2-140">如果已设置，则它可以被应用程序配置文件设置重写。</span><span class="sxs-lookup"><span data-stu-id="26dc2-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="26dc2-141">环境变量名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="26dc2-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="26dc2-142">添加注册表项</span><span class="sxs-lookup"><span data-stu-id="26dc2-142">Adding a registry key</span></span>

  <span data-ttu-id="26dc2-143">可以通过将`REG_DWORD`值添加到注册表中的`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`或`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`键来启用旧的64位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="26dc2-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="26dc2-144">此值的名称`useLegacyJit`为。</span><span class="sxs-lookup"><span data-stu-id="26dc2-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="26dc2-145">如果该值为0，则使用新编译器。</span><span class="sxs-lookup"><span data-stu-id="26dc2-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="26dc2-146">如果值为1，则启用旧版64位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="26dc2-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="26dc2-147">注册表值名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="26dc2-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="26dc2-148">将该值添加到`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`密钥会影响计算机上运行的所有应用。</span><span class="sxs-lookup"><span data-stu-id="26dc2-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="26dc2-149">将该值添加到`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`密钥会影响当前用户运行的所有应用。</span><span class="sxs-lookup"><span data-stu-id="26dc2-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="26dc2-150">如果使用多个用户帐户配置了计算机，则只有当前用户运行的应用才会受到影响，除非还将该值添加到其他用户的注册表项。</span><span class="sxs-lookup"><span data-stu-id="26dc2-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="26dc2-151">如果将`<useLegacyJit>`元素添加到配置文件中，将重写注册表设置（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="26dc2-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26dc2-152">示例</span><span class="sxs-lookup"><span data-stu-id="26dc2-152">Example</span></span>  

<span data-ttu-id="26dc2-153">下面的配置文件使用新的64位 JIT 编译器禁用编译，而改用旧的64位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="26dc2-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="26dc2-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="26dc2-154">See also</span></span>

- [<span data-ttu-id="26dc2-155">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="26dc2-155">\<runtime> Element</span></span>](runtime-element.md)
- [<span data-ttu-id="26dc2-156">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="26dc2-156">\<configuration> Element</span></span>](../configuration-element.md)
- [<span data-ttu-id="26dc2-157">措施新64位 JIT 编译器</span><span class="sxs-lookup"><span data-stu-id="26dc2-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
