---
title: <useLegacyJit> 元素
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d79479d1836963fcbdaaf8d40bfc3648b88c4a3
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2019
ms.locfileid: "69663412"
---
# <a name="uselegacyjit-element"></a>\<useLegacyJit> 元素

确定公共语言运行时是否使用实时编译的旧版 64 位 JIT 编译器。  
  
\<configuration>  
\<运行时 >  
\<useLegacyJit>
  
## <a name="syntax"></a>语法  
  
```xml
<useLegacyJit enabled=0|1 />
```

元素名称`useLegacyJit`区分大小写。
  
## <a name="attributes-and-elements"></a>特性和元素

下列各节描述了特性、子元素和父元素。  
  
### <a name="attributes"></a>特性  
  
| 特性 | 描述                                                                                   |  
| --------- | --------------------------------------------------------------------------------------------- |  
| `enabled` | 必需的特性。<br><br>指定运行时是否使用旧版64位 JIT 编译器。 |  
  
### <a name="enabled-attribute"></a>enabled 属性  
  
| 值 | Description                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | 公共语言运行时使用 .NET Framework 4.6 及更高版本中包含的新64位 JIT 编译器。 |  
| 1     | 公共语言运行时使用较旧的64位 JIT 编译器。                                                     |  
  
### <a name="child-elements"></a>子元素

无
  
### <a name="parent-elements"></a>父元素  
  
| 元素         | 描述                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | 公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。 |  
| `runtime`       | 包含有关运行时初始化选项的信息。                                                        |  
  
## <a name="remarks"></a>备注  

从 .NET Framework 4.6 开始, 默认情况下, 公共语言运行时为实时 (JIT) 编译使用新的64位编译器。 在某些情况下, 这可能会导致应用程序代码的行为与以前版本的64位 JIT 编译器进行 JIT 编译的行为不同。 通过将`<useLegacyJit>`元素`enabled`的属性设置为`1`, 可以禁用新的64位 jit 编译器, 而使用旧的64位 jit 编译器编译应用程序。  
  
> [!NOTE]
> `<useLegacyJit>`元素仅影响64位 JIT 编译。 与32位 JIT 编译器的编译不受影响。  
  
您可以通过两种其他方法启用旧版64位 JIT 编译器, 而不是使用配置文件设置:  
  
- 设置环境变量

  将环境变量设置`0`为 (使用新的64位 jit 编译器) 或`1` (使用较旧的64位 jit 编译器): `COMPLUS_useLegacyJit`
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  环境变量具有*全局作用域*, 这意味着它会影响计算机上运行的所有应用程序。 如果已设置, 则它可以被应用程序配置文件设置重写。 环境变量名称不区分大小写。
  
- 添加注册表项

  可以通过将`REG_DWORD`值添加到注册表中的`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`或`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`键来启用旧的64位 JIT 编译器。 此值的名称`useLegacyJit`为。 如果该值为 0, 则使用新编译器。 如果值为 1, 则启用旧版64位 JIT 编译器。 注册表值名称不区分大小写。
  
  将该值添加到`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`密钥会影响计算机上运行的所有应用。 将该值添加到`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`密钥会影响当前用户运行的所有应用。 如果使用多个用户帐户配置了计算机, 则只有当前用户运行的应用才会受到影响, 除非还将该值添加到其他用户的注册表项。 如果将`<useLegacyJit>`元素添加到配置文件中, 将重写注册表设置 (如果存在)。  
  
## <a name="example"></a>示例  

下面的配置文件使用新的64位 JIT 编译器禁用编译, 而改用旧的64位 JIT 编译器。  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

- [\<运行时 > 元素](runtime-element.md)
- [\<configuration> 元素](../configuration-element.md)
- [措施新64位 JIT 编译器](../../../migration-guide/mitigation-new-64-bit-jit-compiler.md)
