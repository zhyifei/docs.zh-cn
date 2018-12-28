---
title: '&lt;useLegacyJit&gt;元素'
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd4f9728338ecc66f84fe42b9bdbda9938ed518b
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2018
ms.locfileid: "53612187"
---
# <a name="ltuselegacyjitgt-element"></a><span data-ttu-id="e4f42-102">&lt;useLegacyJit&gt;元素</span><span class="sxs-lookup"><span data-stu-id="e4f42-102">&lt;useLegacyJit&gt; Element</span></span>

<span data-ttu-id="e4f42-103">确定公共语言运行时是否使用实时编译的旧版 64 位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="e4f42-103">Determines whether the common language runtime uses the legacy 64-bit JIT compiler for just-in-time compilation.</span></span>  
  
<span data-ttu-id="e4f42-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="e4f42-104">\<configuration></span></span>  
<span data-ttu-id="e4f42-105">\<运行时 ></span><span class="sxs-lookup"><span data-stu-id="e4f42-105">\<runtime></span></span>  
<span data-ttu-id="e4f42-106">\<useLegacyJit ></span><span class="sxs-lookup"><span data-stu-id="e4f42-106">\<useLegacyJit></span></span>
  
## <a name="syntax"></a><span data-ttu-id="e4f42-107">语法</span><span class="sxs-lookup"><span data-stu-id="e4f42-107">Syntax</span></span>  
  
```xml
<useLegacyJit enabled=0|1 />
```

<span data-ttu-id="e4f42-108">元素名称`useLegacyJit`区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e4f42-108">The element name `useLegacyJit` is case-sensitive.</span></span>
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e4f42-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="e4f42-109">Attributes and elements</span></span>

<span data-ttu-id="e4f42-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="e4f42-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e4f42-111">特性</span><span class="sxs-lookup"><span data-stu-id="e4f42-111">Attributes</span></span>  
  
| <span data-ttu-id="e4f42-112">特性</span><span class="sxs-lookup"><span data-stu-id="e4f42-112">Attribute</span></span> | <span data-ttu-id="e4f42-113">描述</span><span class="sxs-lookup"><span data-stu-id="e4f42-113">Description</span></span>                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | <span data-ttu-id="e4f42-114">必需的特性。</span><span class="sxs-lookup"><span data-stu-id="e4f42-114">Required attribute.</span></span><br><br><span data-ttu-id="e4f42-115">指定运行时是否使用旧版 64 位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="e4f42-115">Specifies whether the runtime uses the legacy 64-bit JIT compiler.</span></span> |  
  
### <a name="enabled-attribute"></a><span data-ttu-id="e4f42-116">已启用的属性</span><span class="sxs-lookup"><span data-stu-id="e4f42-116">enabled attribute</span></span>  
  
| <span data-ttu-id="e4f42-117">值</span><span class="sxs-lookup"><span data-stu-id="e4f42-117">Value</span></span> | <span data-ttu-id="e4f42-118">描述</span><span class="sxs-lookup"><span data-stu-id="e4f42-118">Description</span></span>                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| <span data-ttu-id="e4f42-119">0</span><span class="sxs-lookup"><span data-stu-id="e4f42-119">0</span></span>     | <span data-ttu-id="e4f42-120">公共语言运行时使用新的 64 位 JIT 编译器包含在.NET Framework 4.6 和更高版本。</span><span class="sxs-lookup"><span data-stu-id="e4f42-120">The common language runtime uses the new 64-bit JIT compiler included in the .NET Framework 4.6 and later versions.</span></span> |  
| <span data-ttu-id="e4f42-121">1</span><span class="sxs-lookup"><span data-stu-id="e4f42-121">1</span></span>     | <span data-ttu-id="e4f42-122">公共语言运行时使用较旧的 64 位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="e4f42-122">The common language runtime uses the older 64-bit JIT compiler.</span></span>                                                     |  
  
### <a name="child-elements"></a><span data-ttu-id="e4f42-123">子元素</span><span class="sxs-lookup"><span data-stu-id="e4f42-123">Child elements</span></span>

<span data-ttu-id="e4f42-124">无</span><span class="sxs-lookup"><span data-stu-id="e4f42-124">None</span></span>
  
### <a name="parent-elements"></a><span data-ttu-id="e4f42-125">父元素</span><span class="sxs-lookup"><span data-stu-id="e4f42-125">Parent elements</span></span>  
  
| <span data-ttu-id="e4f42-126">元素</span><span class="sxs-lookup"><span data-stu-id="e4f42-126">Element</span></span>         | <span data-ttu-id="e4f42-127">描述</span><span class="sxs-lookup"><span data-stu-id="e4f42-127">Description</span></span>                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | <span data-ttu-id="e4f42-128">公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。</span><span class="sxs-lookup"><span data-stu-id="e4f42-128">The root element in every configuration file used by the common language runtime and .NET Framework applications.</span></span> |  
| `runtime`       | <span data-ttu-id="e4f42-129">包含有关运行时初始化选项的信息。</span><span class="sxs-lookup"><span data-stu-id="e4f42-129">Contains information about runtime initialization options.</span></span>                                                        |  
  
## <a name="remarks"></a><span data-ttu-id="e4f42-130">备注</span><span class="sxs-lookup"><span data-stu-id="e4f42-130">Remarks</span></span>  

<span data-ttu-id="e4f42-131">从.NET Framework 4.6 开始，公共语言运行时使用新的 64 位编译器用于实时 (JIT) 编译默认情况下。</span><span class="sxs-lookup"><span data-stu-id="e4f42-131">Starting with the .NET Framework 4.6, the common language runtime uses a new 64-bit compiler for Just-In-Time (JIT) compilation by default.</span></span> <span data-ttu-id="e4f42-132">在某些情况下，这可能会导致已 JIT 编译的 64 位 JIT 编译器的以前版本的应用程序代码中的行为差异。</span><span class="sxs-lookup"><span data-stu-id="e4f42-132">In some cases, this may result in a difference in behavior from application code that was JIT-compiled by the previous version of the 64-bit JIT compiler.</span></span> <span data-ttu-id="e4f42-133">通过设置`enabled`的属性`<useLegacyJit>`元素`1`，可以禁用新的 64 位 JIT 编译器，并改为编译应用程序使用旧版 64 位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="e4f42-133">By setting the `enabled` attribute of the `<useLegacyJit>` element to `1`, you can disable the new 64-bit JIT compiler and instead compile your app using the legacy 64-bit JIT compiler.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4f42-134">`<useLegacyJit>`元素影响 64 位 JIT 编译。</span><span class="sxs-lookup"><span data-stu-id="e4f42-134">The `<useLegacyJit>` element affects 64-bit JIT compilation only.</span></span> <span data-ttu-id="e4f42-135">使用 32 位 JIT 编译器编译不受影响。</span><span class="sxs-lookup"><span data-stu-id="e4f42-135">Compilation with the 32-bit JIT compiler is unaffected.</span></span>  
  
<span data-ttu-id="e4f42-136">而不是使用配置文件设置，可以启用旧版 64 位 JIT 编译器在两种方法：</span><span class="sxs-lookup"><span data-stu-id="e4f42-136">Instead of using a configuration file setting, you can enable the legacy 64-bit JIT compiler in two other ways:</span></span>  
  
- <span data-ttu-id="e4f42-137">设置环境变量</span><span class="sxs-lookup"><span data-stu-id="e4f42-137">Setting an environment variable</span></span>

  <span data-ttu-id="e4f42-138">设置`COMPLUS_useLegacyJit`为环境变量`0`（使用新的 64 位 JIT 编译器） 或`1`（使用旧版 64 位 JIT 编译器）：</span><span class="sxs-lookup"><span data-stu-id="e4f42-138">Set the `COMPLUS_useLegacyJit` environment variable to either `0` (use the new 64-bit JIT compiler) or `1` (use the older 64-bit JIT compiler):</span></span>
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  <span data-ttu-id="e4f42-139">该环境变量*全局作用域*，这意味着，它会影响在计算机上运行的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="e4f42-139">The environment variable has *global scope*, which means that it affects all applications run on the machine.</span></span> <span data-ttu-id="e4f42-140">如果设置，它可以通过应用程序配置文件设置。</span><span class="sxs-lookup"><span data-stu-id="e4f42-140">If set, it can be overridden by the application configuration file setting.</span></span> <span data-ttu-id="e4f42-141">环境变量名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e4f42-141">The environment variable name is not case-sensitive.</span></span>
  
- <span data-ttu-id="e4f42-142">添加注册表项</span><span class="sxs-lookup"><span data-stu-id="e4f42-142">Adding a registry key</span></span>

  <span data-ttu-id="e4f42-143">可以通过添加启用旧版 64 位 JIT 编译器`REG_DWORD`为值`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`或`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`密钥在注册表中。</span><span class="sxs-lookup"><span data-stu-id="e4f42-143">You can enable the legacy 64-bit JIT compiler by adding a `REG_DWORD` value to either the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` or `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key in the registry.</span></span> <span data-ttu-id="e4f42-144">名为的值`useLegacyJit`。</span><span class="sxs-lookup"><span data-stu-id="e4f42-144">The value is named `useLegacyJit`.</span></span> <span data-ttu-id="e4f42-145">如果值为 0，则使用新的编译器。</span><span class="sxs-lookup"><span data-stu-id="e4f42-145">If the value is 0, the new compiler is used.</span></span> <span data-ttu-id="e4f42-146">如果值为 1，则启用旧版 64 位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="e4f42-146">If the value is 1, the legacy 64-bit JIT compiler is enabled.</span></span> <span data-ttu-id="e4f42-147">注册表值名称不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e4f42-147">The registry value name is not case-sensitive.</span></span>
  
  <span data-ttu-id="e4f42-148">添加到值`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`密钥会影响在计算机上运行的所有应用。</span><span class="sxs-lookup"><span data-stu-id="e4f42-148">Adding the value to the `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework` key affects all apps running on the machine.</span></span> <span data-ttu-id="e4f42-149">添加到值`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`密钥会影响在当前用户运行的所有应用。</span><span class="sxs-lookup"><span data-stu-id="e4f42-149">Adding the value to the `HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework` key affects all apps run by the current user.</span></span> <span data-ttu-id="e4f42-150">如果一台计算机配置了多个用户帐户，只能由当前用户运行的应用程序会影响，除非将值添加到其他用户的注册表项。</span><span class="sxs-lookup"><span data-stu-id="e4f42-150">If a machine is configured with multiple user accounts, only apps run by the current user are affected, unless the value is added to the registry keys for other users as well.</span></span> <span data-ttu-id="e4f42-151">添加`<useLegacyJit>`到配置文件的元素会替代注册表设置中，如果它们存在。</span><span class="sxs-lookup"><span data-stu-id="e4f42-151">Adding the `<useLegacyJit>` element to a configuration file overrides the registry settings, if they're present.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e4f42-152">示例</span><span class="sxs-lookup"><span data-stu-id="e4f42-152">Example</span></span>  

<span data-ttu-id="e4f42-153">下面的配置文件禁用使用新的 64 位 JIT 编译器进行编译，而是使用旧版 64 位 JIT 编译器。</span><span class="sxs-lookup"><span data-stu-id="e4f42-153">The following configuration file disables compilation with the new 64-bit JIT compiler and instead uses the legacy 64-bit JIT compiler.</span></span>  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e4f42-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="e4f42-154">See also</span></span>

- [<span data-ttu-id="e4f42-155">\<运行时 > 元素</span><span class="sxs-lookup"><span data-stu-id="e4f42-155">\<runtime> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)   
- [<span data-ttu-id="e4f42-156">\<configuration> 元素</span><span class="sxs-lookup"><span data-stu-id="e4f42-156">\<configuration> Element</span></span>](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)   
- [<span data-ttu-id="e4f42-157">缓解：新的 64 位 JIT 编译器</span><span class="sxs-lookup"><span data-stu-id="e4f42-157">Mitigation: New 64-bit JIT Compiler</span></span>](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
