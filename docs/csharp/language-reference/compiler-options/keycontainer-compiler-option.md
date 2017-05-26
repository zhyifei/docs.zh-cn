---
title: "-keycontainer（C# 编译器选项）| Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /keycontainer
dev_langs:
- CSharp
helpviewer_keywords:
- /keycontainer compiler option [C#]
- keycontainer compiler option [C#]
- -keycontainer compiler option [C#]
ms.assetid: b3982b6d-2382-4f7e-bebd-ce98eaa30763
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: fe32676f0e39ed109a68f39584cf41aec5f5ce90
ms.openlocfilehash: 30b851a3e44c90582227beda7245a7c4b0d57b47
ms.contentlocale: zh-cn
ms.lasthandoff: 05/10/2017

---
# <a name="keycontainer-c-compiler-options"></a>/keycontainer（C# 编译器选项）
指定加密密钥容器的名称。  
  
## <a name="syntax"></a>语法  
  
```  
/keycontainer:string  
```  
  
## <a name="arguments"></a>参数  
 `string`  
 强名称密钥容器的名称。  
  
## <a name="remarks"></a>备注  
 使用“/keycontainer”选项时，通过将来自所指定容器的公钥插入到程序集清单并且用私钥签名最终程序集，编译器可创建可共享的组件。 若要生成密钥文件，请在命令行键入 sn-k `file`。 sn-i 将密钥对安装到容器中。  
  
 如果使用 [/target: module](../../../csharp/language-reference/compiler-options/target-module-compiler-option.md) 进行编译，当使用 [/addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md) 将此模块编译到程序集时，密钥文件的名称将保存在模块中，且会并入程序集。  
  
 还可以将此选项指定为任何 Microsoft 中间语言 (MSIL) 模块的源代码中的自定义特性 (<xref:System.Reflection.AssemblyKeyNameAttribute?displayProperty=fullName>)。  
  
 此外，可使用 [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) 将加密信息传递给编译器。 如果希望将公钥添加到程序集清单，但希望测试完程序集后再对其签名，请使用 [/delaysign](../../../csharp/language-reference/compiler-options/delaysign-compiler-option.md)。  
  
 有关详细信息，请参阅[创建和使用具有强名称的程序集](https://msdn.microsoft.com/library/xwb8f617)和[延迟为程序集签名](../../../framework/app-domains/delay-sign-assembly.md)。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项  
  
1.  Visual Studio 开发环境中尚未提供此编译器选项。  
  
 可通过 <xref:VSLangProj.ProjectProperties.AssemblyKeyContainerName%2A> 以编程方式访问此编译器选项。  
  
## <a name="see-also"></a>另请参阅  
 [（C# 编译器选项）](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB 如何：修改项目属性和配置设置](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
