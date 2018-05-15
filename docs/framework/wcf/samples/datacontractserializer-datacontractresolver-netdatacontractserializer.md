---
title: 使用 DataContractSerializer 和 DataContractResolver 实现 NetDataContractSerializer 的功能
ms.date: 03/30/2017
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
ms.openlocfilehash: a9dde936f2daff669aabe36c5f03203a472d435c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a><span data-ttu-id="5eae0-102">使用 DataContractSerializer 和 DataContractResolver 实现 NetDataContractSerializer 的功能</span><span class="sxs-lookup"><span data-stu-id="5eae0-102">Using DataContractSerializer and DataContractResolver to Provide the Functionality of NetDataContractSerializer</span></span>
<span data-ttu-id="5eae0-103">此示例演示如何将 <xref:System.Runtime.Serialization.DataContractSerializer> 与相应的 <xref:System.Runtime.Serialization.DataContractResolver> 结合使用来提供与 <xref:System.Runtime.Serialization.NetDataContractSerializer> 相同的功能。</span><span class="sxs-lookup"><span data-stu-id="5eae0-103">This sample demonstrates how the use of <xref:System.Runtime.Serialization.DataContractSerializer> with an appropriate <xref:System.Runtime.Serialization.DataContractResolver> provides the same functionality as <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="5eae0-104">此示例演示如何创建相应的 <xref:System.Runtime.Serialization.DataContractResolver> 以及如何将其添加到 <xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="5eae0-104">This sample shows how to create the appropriate <xref:System.Runtime.Serialization.DataContractResolver> and how to add it to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>  
  
## <a name="sample-details"></a><span data-ttu-id="5eae0-105">示例详细信息</span><span class="sxs-lookup"><span data-stu-id="5eae0-105">Sample details</span></span>  
 <span data-ttu-id="5eae0-106"><xref:System.Runtime.Serialization.NetDataContractSerializer> 与 <xref:System.Runtime.Serialization.DataContractSerializer> 之间存在一个重要区别：<xref:System.Runtime.Serialization.NetDataContractSerializer> 在序列化的 XML 中包含 CLR 类型信息，而 <xref:System.Runtime.Serialization.DataContractSerializer> 不包含这种信息。</span><span class="sxs-lookup"><span data-stu-id="5eae0-106"><xref:System.Runtime.Serialization.NetDataContractSerializer> differs from <xref:System.Runtime.Serialization.DataContractSerializer> in one important way: <xref:System.Runtime.Serialization.NetDataContractSerializer> includes CLR type information in the serialized XML, whereas <xref:System.Runtime.Serialization.DataContractSerializer> does not.</span></span> <span data-ttu-id="5eae0-107">因此，只有在序列化和反序列化端共享相同的 CLR 类型时，才能使用 <xref:System.Runtime.Serialization.NetDataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="5eae0-107">Therefore, <xref:System.Runtime.Serialization.NetDataContractSerializer> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="5eae0-108">但是，建议使用 <xref:System.Runtime.Serialization.DataContractSerializer>，因为其性能比 <xref:System.Runtime.Serialization.NetDataContractSerializer> 更佳。</span><span class="sxs-lookup"><span data-stu-id="5eae0-108">However, it is recommended to use <xref:System.Runtime.Serialization.DataContractSerializer> because its performance is better than <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="5eae0-109">通过将 <xref:System.Runtime.Serialization.DataContractSerializer> 添加到 <xref:System.Runtime.Serialization.DataContractResolver>，可以更改在其中序列化的信息。</span><span class="sxs-lookup"><span data-stu-id="5eae0-109">You can change the information that is serialized in <xref:System.Runtime.Serialization.DataContractSerializer> by adding a <xref:System.Runtime.Serialization.DataContractResolver> to it.</span></span>  
  
 <span data-ttu-id="5eae0-110">此示例由两个项目组成。</span><span class="sxs-lookup"><span data-stu-id="5eae0-110">This sample consists of two projects.</span></span> <span data-ttu-id="5eae0-111">第一个项目使用 <xref:System.Runtime.Serialization.NetDataContractSerializer> 来序列化对象。</span><span class="sxs-lookup"><span data-stu-id="5eae0-111">The first project uses <xref:System.Runtime.Serialization.NetDataContractSerializer> to serialize an object.</span></span> <span data-ttu-id="5eae0-112">第二个项目将 <xref:System.Runtime.Serialization.DataContractSerializer> 与 <xref:System.Runtime.Serialization.DataContractResolver> 结合使用，以提供与第一个项目相同的功能。</span><span class="sxs-lookup"><span data-stu-id="5eae0-112">The second project uses <xref:System.Runtime.Serialization.DataContractSerializer> with a <xref:System.Runtime.Serialization.DataContractResolver> to provide the same functionality as the first project.</span></span>  
  
 <span data-ttu-id="5eae0-113">以下代码示例演示如何实现名为 <xref:System.Runtime.Serialization.DataContractResolver> 的自定义 `MyDataContractResolver`，后者将添加到 DCSwithDCR 项目中的  <xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="5eae0-113">The following code example shows the implementation of a custom <xref:System.Runtime.Serialization.DataContractResolver> named `MyDataContractResolver` that is added to the <xref:System.Runtime.Serialization.DataContractSerializer> in the DCSwithDCR project.</span></span>  
  
```  
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
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="5eae0-114">使用此示例</span><span class="sxs-lookup"><span data-stu-id="5eae0-114">To use this sample</span></span>  
  
1.  <span data-ttu-id="5eae0-115">使用 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 打开 DCRSample.sln 解决方案文件。</span><span class="sxs-lookup"><span data-stu-id="5eae0-115">Using [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)], open the DCRSample.sln solution file.</span></span>  
  
2.  <span data-ttu-id="5eae0-116">右键单击解决方案文件并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="5eae0-116">Right-click the solution file and choose **Properties**.</span></span>  
  
3.  <span data-ttu-id="5eae0-117">在**解决方案属性页**对话框下**通用属性**，**启动项目**，选择**多启动项目：**。</span><span class="sxs-lookup"><span data-stu-id="5eae0-117">In the **Solution Property Pages** dialog, under **Common Properties**, **Startup Project**, select **Multiple startup projects:**.</span></span>  
  
4.  <span data-ttu-id="5eae0-118">旁边**DCSwithDCR**项目，依次选择**启动**从**操作**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="5eae0-118">Next to the **DCSwithDCR** project, select **Start** from the **Action** dropdown.</span></span>  
  
5.  <span data-ttu-id="5eae0-119">旁边**NetDCS**项目，依次选择**启动**从**操作**下拉列表。</span><span class="sxs-lookup"><span data-stu-id="5eae0-119">Next to the **NetDCS** project, select **Start** from the **Action** dropdown.</span></span>  
  
6.  <span data-ttu-id="5eae0-120">单击**确定**关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="5eae0-120">Click **OK** to close the dialog.</span></span>  
  
7.  <span data-ttu-id="5eae0-121">要生成解决方案，按 Ctrl+Shift+B。</span><span class="sxs-lookup"><span data-stu-id="5eae0-121">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
8.  <span data-ttu-id="5eae0-122">若要运行解决方案，请按 Ctrl+F5。</span><span class="sxs-lookup"><span data-stu-id="5eae0-122">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="5eae0-123">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="5eae0-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="5eae0-124">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="5eae0-124">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="5eae0-125">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和针对.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780)下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="5eae0-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="5eae0-126">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="5eae0-126">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
  
## <a name="see-also"></a><span data-ttu-id="5eae0-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="5eae0-127">See Also</span></span>
