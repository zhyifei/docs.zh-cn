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
ms.openlocfilehash: 7ebafcf446c9033c93e0c5fa5e11ea2930bd2e1e
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602555"
---
# <a name="-preferreduilang-c-compiler-options"></a>-preferreduilang（C# 编译器选项）
通过使用 `-preferreduilang` 编译器选项，可指定 C# 编译器显示输出的语言，如错误消息。  
  
## <a name="syntax"></a>语法  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a>自变量  
 `language`  
 用于编译器输出的语言的[语言名称](/windows/desktop/Intl/language-names)。  
  
## <a name="remarks"></a>备注  
 可以使用 `-preferreduilang` 编译器选项指定 C# 编译器用于错误消息和其他命令行输出的语言。 如果未安装针对该语言的语言包，将改用操作系统的语言设置，而不会报告错误。  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a>要求  
  
## <a name="see-also"></a>请参阅

- [C# 编译器选项](./index.md)
