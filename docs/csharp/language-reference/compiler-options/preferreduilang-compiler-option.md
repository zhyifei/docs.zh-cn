---
title: -preferreduilang（C# 编译器选项）
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: 21a3baceb8a46723de1c633e415af0660bb41840
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-preferreduilang-c-compiler-options"></a>-preferreduilang（C# 编译器选项）
通过使用 `-preferreduilang` 编译器选项，可指定 C# 编译器显示输出的语言，如错误消息。  
  
## <a name="syntax"></a>语法  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a>自变量  
 `language`  
 用于编译器输出的语言的[语言名称](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx)。  
  
## <a name="remarks"></a>备注  
 可以使用 `-preferreduilang` 编译器选项指定 C# 编译器用于错误消息和其他命令行输出的语言。 如果未安装针对该语言的语言包，将改用操作系统的语言设置，而不会报告错误。  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>惠?  
  
## <a name="see-also"></a>请参阅  
 [C# 编译器选项](../../../csharp/language-reference/compiler-options/index.md)
