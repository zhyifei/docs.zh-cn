---
ms.openlocfilehash: 1805c26f1eff46719f30de8a14ca6d35f01948a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774299"
---
### <a name="foreach-iterator-variable-is-now-scoped-within-the-iteration-so-closure-capturing-semantics-are-different-in-c5"></a>Foreach 迭代器变量现在已在迭代范围内，因此闭包捕获语义会不同（在 C#5 中）

|   |   |
|---|---|
|详细信息|从 C# 5 (Visual Studio 2012) 开始，<code>foreach</code> 迭代器变量在迭代范围内。 如果代码以前依靠变量而不在 <code>foreach</code> 闭包内，这可能会导致中断。 此更改的特征如下：传递到委托的迭代器变量将视为委托创建时它拥有的值，而非调用委托时它拥有的值。|
|建议|理想情况下，应更新代码以使用新的编译器行为。 如果需要旧语义，迭代器变量可替换为显式置于循环范围外的单独变量。|
|范围|主要|
|版本|4.5|
|类型|重定目标|
