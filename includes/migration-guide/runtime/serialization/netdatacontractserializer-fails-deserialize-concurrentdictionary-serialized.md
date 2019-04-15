---
ms.openlocfilehash: 380f662349a8dcd04e5bf445e1479d0a32d5861f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59235173"
---
### <a name="netdatacontractserializer-fails-to-deserialize-a-concurrentdictionary-serialized-with-a-different-net-version"></a>NetDataContractSerializer 无法反序列化使用其他 .NET 版本序列化的 ConcurrentDictionary

|   |   |
|---|---|
|详细信息|根据设计，只有在序列化和反序列化端共享相同的 CLR 类型时，才能使用 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>。 因此，无法保证使用某个版本的 .NET Framework 序列化的对象可由其他版本反序列化。<xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name> 是一种类型，已知该类型如果使用 .NET Framework 4.5 或更早版本序列化并使用 .NET Framework 4.5.1 或更早版本反序列化，则无法正确反序列化。|
|建议|针对这个问题有很多可行的解决方法：<ul><li>升级序列化计算机以使用 .NET Framework 4.5.1。</li><li>使用 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> 而不是 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name>，因为这并不指望在序列化端和反序列化端具有完全相同的 CLR 类型。</li><li>使用 <xref:System.Collections.Generic.Dictionary%602?displayProperty=name> 而不是 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name>，因为它不会显示出特定的 4.5-&gt;4.5.1 中断。</li></ul>|
|范围|次要|
|版本|4.5.1|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Runtime.Serialization.NetDataContractSerializer.Deserialize(System.IO.Stream)?displayProperty=nameWithType></li></ul>|
