---
title: "-delaysign（C# 编译器选项）| Microsoft Docs"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /delaysign
dev_langs:
- CSharp
helpviewer_keywords:
- -delaysign compiler option [C#]
- delaysign compiler option [C#]
- /delaysign compiler option [C#]
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: 16
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
ms.openlocfilehash: f3dc76214acb66f2212a3611c0c419889e58c359
ms.contentlocale: zh-cn
ms.lasthandoff: 05/10/2017

---
# <a name="delaysign-c-compiler-options"></a>/delaysign（C# 编译器选项）
此选项会使编译器在输出文件中保留空间，以便以后添加数字签名。  
  
## <a name="syntax"></a>语法  
  
```console  
/delaysign[ + | - ]  
```  
  
## <a name="arguments"></a>参数  
 `+` &#124; `-`  
 如果需要完全签名的程序集，请使用 **/delaysign-**。 如果仅需要将公钥置于程序集中，则使用 /delaysign+。 默认值为 **/delaysign-**。  
  
## <a name="remarks"></a>备注  
 除非与 [/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) 或 [/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md) 一同使用，否则 /delaysign 选项将不起作用。  
  
 在请求完全签名的程序集时，编译器会对包含清单（程序集元数据）的文件进行哈希处理，并使用私钥对哈希进行签名。 产生的数字签名存储在包含清单的文件中。 在对程序集延迟签名时，编译器不会计算和存储签名，而只是在文件中保留空间以便稍后可添加签名。  
  
 例如，使用 /delaysign+ 可允许测试人员将程序集放入全局缓存中。 测试完成后，可使用[程序集链接器](https://msdn.microsoft.com/library/c405shex)实用工具将私钥置于程序集中，对程序集进行完全签名。  
  
 有关详细信息，请参阅[创建和使用具有强名称的程序集](https://msdn.microsoft.com/library/xwb8f617)和[延迟为程序集签名](../../../framework/app-domains/delay-sign-assembly.md)。  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项  
  
1.  打开项目的“属性”  页。  
  
2.  修改“仅延迟签名”属性。  
  
 有关如何以编程方式设置此编译器选项的信息，请参阅 <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>。  
  
## <a name="see-also"></a>另请参阅  
 [（C# 编译器选项）](../../../csharp/language-reference/compiler-options/index.md)   
 [NIB 如何：修改项目属性和配置设置](http://msdn.microsoft.com/en-us/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)
