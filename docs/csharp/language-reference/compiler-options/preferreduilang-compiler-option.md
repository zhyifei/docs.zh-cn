---
title: "-preferreduilang（C# 编译器选项）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a96a054b3d1f73b0fee209557388f7ea213ebbe9
ms.sourcegitcommit: 401c4427a3ec0d1263543033b3084039278509dc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/06/2017
---
# <a name="preferreduilang-c-compiler-options"></a>/preferreduilang（C# 编译器选项）
通过使用 `/preferreduilang` 编译器选项，可指定 C# 编译器显示输出的语言，如错误消息。  
  
## <a name="syntax"></a>语法  
  
```console  
/preferreduilang: language  
```  
  
## <a name="arguments"></a>参数  
 `language`  
 用于编译器输出的语言的[语言名称](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx)。  
  
## <a name="remarks"></a>备注  
 可以使用 `/preferreduilang` 编译器选项指定 C# 编译器用于错误消息和其他命令行输出的语言。 如果未安装针对该语言的语言包，将改用操作系统的语言设置，而不会报告错误。  
  
```csharp  
csc.exe /preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>要求  
  
## <a name="see-also"></a>另请参阅  
 [C# 编译器选项](../../../csharp/language-reference/compiler-options/index.md)
