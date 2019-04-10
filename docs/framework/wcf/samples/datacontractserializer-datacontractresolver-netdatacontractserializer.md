---
title: 使用 DataContractSerializer 和 DataContractResolver 实现 NetDataContractSerializer 的功能
ms.date: 03/30/2017
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
ms.openlocfilehash: 455ffe936373525f574d4401412c099d41d45f66
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59167214"
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a><span data-ttu-id="961c4-102">使用 DataContractSerializer 和 DataContractResolver 实现 NetDataContractSerializer 的功能</span><span class="sxs-lookup"><span data-stu-id="961c4-102">Using DataContractSerializer and DataContractResolver to Provide the Functionality of NetDataContractSerializer</span></span>
<span data-ttu-id="961c4-103">此示例演示如何将 <xref:System.Runtime.Serialization.DataContractSerializer> 与相应的 <xref:System.Runtime.Serialization.DataContractResolver> 结合使用来提供与 <xref:System.Runtime.Serialization.NetDataContractSerializer> 相同的功能。</span><span class="sxs-lookup"><span data-stu-id="961c4-103">This sample demonstrates how the use of <xref:System.Runtime.Serialization.DataContractSerializer> with an appropriate <xref:System.Runtime.Serialization.DataContractResolver> provides the same functionality as <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="961c4-104">此示例演示如何创建相应的 <xref:System.Runtime.Serialization.DataContractResolver> 以及如何将其添加到 <xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="961c4-104">This sample shows how to create the appropriate <xref:System.Runtime.Serialization.DataContractResolver> and how to add it to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

## <a name="sample-details"></a><span data-ttu-id="961c4-105">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="961c4-105">Sample details</span></span>
 <xref:System.Runtime.Serialization.NetDataContractSerializer> <span data-ttu-id="961c4-106">不同于<xref:System.Runtime.Serialization.DataContractSerializer>重要的一种方法中：<xref:System.Runtime.Serialization.NetDataContractSerializer>包括序列化的 XML 中的 CLR 类型信息，而<xref:System.Runtime.Serialization.DataContractSerializer>却没有。</span><span class="sxs-lookup"><span data-stu-id="961c4-106">differs from <xref:System.Runtime.Serialization.DataContractSerializer> in one important way: <xref:System.Runtime.Serialization.NetDataContractSerializer> includes CLR type information in the serialized XML, whereas <xref:System.Runtime.Serialization.DataContractSerializer> does not.</span></span> <span data-ttu-id="961c4-107">因此，只有在序列化和反序列化端共享相同的 CLR 类型时，才能使用 <xref:System.Runtime.Serialization.NetDataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="961c4-107">Therefore, <xref:System.Runtime.Serialization.NetDataContractSerializer> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="961c4-108">但是，建议使用 <xref:System.Runtime.Serialization.DataContractSerializer>，因为其性能比 <xref:System.Runtime.Serialization.NetDataContractSerializer> 更佳。</span><span class="sxs-lookup"><span data-stu-id="961c4-108">However, it is recommended to use <xref:System.Runtime.Serialization.DataContractSerializer> because its performance is better than <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="961c4-109">通过将 <xref:System.Runtime.Serialization.DataContractSerializer> 添加到 <xref:System.Runtime.Serialization.DataContractResolver>，可以更改在其中序列化的信息。</span><span class="sxs-lookup"><span data-stu-id="961c4-109">You can change the information that is serialized in <xref:System.Runtime.Serialization.DataContractSerializer> by adding a <xref:System.Runtime.Serialization.DataContractResolver> to it.</span></span>

 <span data-ttu-id="961c4-110">此示例由两个项目组成。</span><span class="sxs-lookup"><span data-stu-id="961c4-110">This sample consists of two projects.</span></span> <span data-ttu-id="961c4-111">第一个项目使用 <xref:System.Runtime.Serialization.NetDataContractSerializer> 来序列化对象。</span><span class="sxs-lookup"><span data-stu-id="961c4-111">The first project uses <xref:System.Runtime.Serialization.NetDataContractSerializer> to serialize an object.</span></span> <span data-ttu-id="961c4-112">第二个项目将 <xref:System.Runtime.Serialization.DataContractSerializer> 与 <xref:System.Runtime.Serialization.DataContractResolver> 结合使用，以提供与第一个项目相同的功能。</span><span class="sxs-lookup"><span data-stu-id="961c4-112">The second project uses <xref:System.Runtime.Serialization.DataContractSerializer> with a <xref:System.Runtime.Serialization.DataContractResolver> to provide the same functionality as the first project.</span></span>

 <span data-ttu-id="961c4-113">以下代码示例演示如何实现名为 <xref:System.Runtime.Serialization.DataContractResolver> 的自定义 `MyDataContractResolver`，后者将添加到 DCSwithDCR 项目中的  <xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="961c4-113">The following code example shows the implementation of a custom <xref:System.Runtime.Serialization.DataContractResolver> named `MyDataContractResolver` that is added to the <xref:System.Runtime.Serialization.DataContractSerializer> in the DCSwithDCR project.</span></span>

```csharp
class MyDataContractResolver : DataContractResolver
{
    private XmlDictionary dictionary = new XmlDictionary();

    public MyDataContractResolver()
    {
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);
        if (type == null)
        {
            type = Type.GetType(typeName + ", " + typeNamespace);
        }
        return type;
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);
        if (typeName == null || typeNamespace == null)
        {
            XmlDictionary dictionary = new XmlDictionary();
            typeName = dictionary.Add(dataContractType.FullName);
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);
        }
    }
}
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="961c4-114">使用此示例</span><span class="sxs-lookup"><span data-stu-id="961c4-114">To use this sample</span></span>

1.  <span data-ttu-id="961c4-115">使用 Visual Studio 2012 打开 DCRSample.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="961c4-115">Using Visual Studio 2012, open the DCRSample.sln solution file.</span></span>

2.  <span data-ttu-id="961c4-116">右键单击解决方案文件，然后选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="961c4-116">Right-click the solution file and choose **Properties**.</span></span>

3.  <span data-ttu-id="961c4-117">在中**解决方案属性页**对话框下**通用属性**，**启动项目**，选择**多个启动项目：**。</span><span class="sxs-lookup"><span data-stu-id="961c4-117">In the **Solution Property Pages** dialog, under **Common Properties**, **Startup Project**, select **Multiple startup projects:**.</span></span>

4.  <span data-ttu-id="961c4-118">下一步**DCSwithDCR**项目，选择**启动**从**操作**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="961c4-118">Next to the **DCSwithDCR** project, select **Start** from the **Action** dropdown.</span></span>

5.  <span data-ttu-id="961c4-119">下一步**NetDCS**项目，选择**启动**从**操作**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="961c4-119">Next to the **NetDCS** project, select **Start** from the **Action** dropdown.</span></span>

6.  <span data-ttu-id="961c4-120">单击**确定**关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="961c4-120">Click **OK** to close the dialog.</span></span>

7.  <span data-ttu-id="961c4-121">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="961c4-121">To build the solution, press CTRL+SHIFT+B.</span></span>

8.  <span data-ttu-id="961c4-122">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="961c4-122">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="961c4-123">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="961c4-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="961c4-124">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="961c4-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="961c4-125">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="961c4-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="961c4-126">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="961c4-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
