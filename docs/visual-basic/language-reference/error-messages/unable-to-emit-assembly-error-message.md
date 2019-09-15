---
title: 无法发出程序集：<error message>
ms.date: 08/14/2018
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
ms.openlocfilehash: 530aaee40be92bf72ee4b83b4141108e9b81c8a1
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/13/2019
ms.locfileid: "70968854"
---
# <a name="unable-to-emit-assembly-error-message"></a>无法发出程序集： \<错误消息 >

Visual Basic 编译器调用程序集链接器（*al.exe*，也称为 Alink）来生成包含清单的程序集，而链接器在创建程序集的排放阶段报告错误。

**错误 ID：** BC30145

## <a name="to-correct-this-error"></a>更正此错误

1. 检查引用的错误消息并查阅[al.exe](../../../framework/tools/al-exe-assembly-linker.md) ，以获取进一步的说明和建议。

2. 尝试使用[al.exe](../../../framework/tools/al-exe-assembly-linker.md)或[Sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)手动对程序集进行签名。

3. 如果仍然出现错误，则收集有关该情况的信息并通知 Microsoft 产品支持服务。

### <a name="to-sign-the-assembly-manually"></a>手动对程序集进行签名

1. 使用[sn.exe （强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)创建公钥/私钥对文件。

   此文件的扩展名为 *.snk* 。

2. 从项目中删除生成错误的 COM 引用。

3. 打开[Visual Studio 的开发人员命令提示](../../../framework/tools/developer-command-prompt-for-vs.md)。

   在 Windows 10 中，在任务栏上的搜索框中输入 "**开发人员命令提示**"。 然后，从结果列表中选择**VS 2017 开发人员命令提示**。

4. 将目录更改为要在其中放置程序集包装的目录。

5. 输入以下命令：

    ```cmd
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>
    ```

   你可能会输入的实际命令的示例如下：

    ```cmd
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"
    ```

   > [!TIP]
   > 如果路径或文件包含空格，请使用双引号。

6. 在 Visual Studio 中，将 .NET 程序集引用添加到刚创建的文件。

## <a name="see-also"></a>请参阅

- [Al.exe](../../../framework/tools/al-exe-assembly-linker.md)
- [Sn.exe（强名称工具）](../../../framework/tools/sn-exe-strong-name-tool.md)
- [如何：创建公钥/私钥对](../../../standard/assembly/create-public-private-key-pair.md)
- [与我们交流](/visualstudio/ide/talk-to-us)
