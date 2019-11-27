---
title: 变量使用了不支持的自动化类型
ms.date: 07/20/2015
f1_keywords:
- vbrID458
ms.assetid: bde4f4da-493b-452c-b6e4-1d370edba4cd
ms.openlocfilehash: 944c0c63cd0d7ae7f9ff770fd123231464af1eaf
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344830"
---
# <a name="variable-uses-an-automation-type-not-supported-in-visual-basic"></a>变量使用了 Visual Basic 不支持的自动化类型

尝试使用类型库或对象库中定义的变量，该变量的数据类型不受 Visual Basic 支持。

## <a name="to-correct-this-error"></a>更正此错误

- 使用 Visual Basic 可识别的类型的变量。

     \- 或 -

- 如果使用 `FileGet` 或 `FileGetObject`时遇到此错误，请确保使用 `FilePut` 或 `FilePutObject`写入尝试使用的文件。

## <a name="see-also"></a>另请参阅

- [数据类型](../../../visual-basic/language-reference/data-types/index.md)
