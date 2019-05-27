---
title: -codepage（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /codepage
helpviewer_keywords:
- /codepage compiler option [C#]
- codepage compiler option [C#]
- -codepage compiler option [C#]
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
ms.openlocfilehash: 59dc1abc3f678a4cf15543c11f9f200ff318ce8f
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65876929"
---
# <a name="-codepage-c-compiler-options"></a>-codepage（C# 编译器选项）
如果所需页不是系统的当前默认代码页，则此选项指定编译期间要使用的代码页。  
  
## <a name="syntax"></a>语法  
  
```console  
-codepage:id  
```  
  
## <a name="arguments"></a>自变量  
 `id`  
 要用于编译中所有源代码文件的代码页 ID。  
  
## <a name="remarks"></a>备注  
 编译器将首先尝试将所有源文件解释为 UTF-8。 如果源代码文件使用除 UTF-8 以外的编码并使用除 7 位 ASCII 字符以外的字符，请使用 -codepage 选项指定应使用的代码页。 -codepage 适用于编译中的所有源代码文件。  
    
 有关如何查找系统上支持哪些代码页的信息，请参阅 [GetCPInfo](/windows/desktop/api/winnls/nf-winnls-getcpinfo)。  
  
 此编译器选项在 Visual Studio 中不可用，并且无法以编程方式更改。  
  
## <a name="see-also"></a>请参阅

- [C# 编译器选项](../../../csharp/language-reference/compiler-options/index.md)
- [管理项目和解决方案属性](/visualstudio/ide/managing-project-and-solution-properties)
