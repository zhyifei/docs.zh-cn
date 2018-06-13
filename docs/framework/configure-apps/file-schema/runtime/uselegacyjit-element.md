---
title: '&lt;useLegacyJit&gt;元素'
ms.date: 04/26/2017
ms.assetid: c2cf97f0-9262-4f1f-a754-5568b51110ad
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd0ae1a44b41ddcae2149bcf685871a37dd01b06
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32746769"
---
# <a name="ltuselegacyjitgt-element"></a>&lt;useLegacyJit&gt;元素

确定公共语言运行时是否使用实时编译的旧版 64 位 JIT 编译器。  
  
\<configuration>  
\<运行时 >  
\<useLegacyJit >
  
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
| `enabled` | 必需的特性。<br><br>指定运行时是否使用旧的 64 位 JIT 编译器。 |  
  
### <a name="enabled-attribute"></a>enabled 的特性  
  
| 值 | 描述                                                                                                         |  
| ----- | ------------------------------------------------------------------------------------------------------------------- |  
| 0     | 公共语言运行时使用新的 64 位 JIT 编译器包含在.NET Framework 4.6 和更高版本。 |  
| 1     | 公共语言运行时使用较旧的 64 位 JIT 编译器。                                                     |  
  
### <a name="child-elements"></a>子元素

无
  
### <a name="parent-elements"></a>父元素  
  
| 元素         | 描述                                                                                                       |  
| --------------- | ----------------------------------------------------------------------------------------------------------------- |  
| `configuration` | 公共语言运行时和 .NET Framework 应用程序所使用的每个配置文件中的根元素。 |  
| `runtime`       | 包含有关运行时初始化选项的信息。                                                        |  
  
## <a name="remarks"></a>备注  

从.NET Framework 4.6 开始，公共语言运行时使用新的 64 位编译器实时 (JIT) 编译为默认情况下。 在某些情况下，这可能会导致已 JIT 编译的 64 位 JIT 编译器的以前版本的应用程序代码中的行为差异。 通过设置`enabled`属性`<useLegacyJit>`元素`1`，可以禁用新的 64 位 JIT 编译器，并改为使用旧的 64 位 JIT 编译器将应用程序进行编译。  
  
> [!NOTE]
> `<useLegacyJit>`元素影响仅 64 位 JIT 编译。 使用 32 位 JIT 编译器编译不受影响。  
  
而不是使用配置文件设置，你可以启用旧的 64 位 JIT 编译器，另外两种：  
  
- 设置环境变量

  设置`COMPLUS_useLegacyJit`为环境变量`0`（使用新的 64 位 JIT 编译器） 或`1`（使用旧的 64 位 JIT 编译器）：
  
  ```  
  COMPLUS_useLegacyJit=0|1  
  ```  
  
  环境变量具有*全局范围内*，这意味着它所影响的计算机上运行的所有应用程序。 如果设置，它可重写应用程序配置文件设置。 环境变量名称不区分大小写。
  
- 添加注册表项

  你可以通过添加启用旧的 64 位 JIT 编译器`REG_DWORD`值为`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`或`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`注册表中的键。 名为的值`useLegacyJit`。 如果值为 0，则使用新的编译器。 如果值为 1，则启用旧的 64 位 JIT 编译器。 注册表值名称不区分大小写。
  
  添加到值`HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework`密钥会影响的计算机上运行的所有应用。 添加到值`HKEY_CURRENT_USER\SOFTWARE\Microsoft\.NETFramework`密钥会影响由当前用户运行的所有应用。 如果计算机配置为使用多个用户帐户，仅由当前用户运行的应用受到影响，除非将值添加到以及其他用户的注册表项。 添加`<useLegacyJit>`到配置文件的元素会替代注册表设置，如果他们是存在。  
  
## <a name="example"></a>示例  

下面的配置文件禁用使用新的 64 位 JIT 编译器的编译，而是使用旧的 64 位 JIT 编译器。  
  
```xml  
<?xml version ="1.0"?>  
<configuration>  
  <runtime>  
    <useLegacyJit enabled="1" />  
  </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a>请参阅

[\<运行时 > 元素](../../../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md)   
[\<配置 > 元素](../../../../../docs/framework/configure-apps/file-schema/configuration-element.md)   
[缓解：新的 64 位 JIT 编译器](../../../../../docs/framework/migration-guide/mitigation-new-64-bit-jit-compiler.md)
