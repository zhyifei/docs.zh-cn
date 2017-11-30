---
title: "演练：创建数据流管道"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- dataflow pipelines, creating with TPL
- Task Parallel Library, dataflows
- TPL dataflow library, creating dataflow pipeline
ms.assetid: 69308f82-aa22-4ac5-833d-e748533b58e8
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d63fb872382bfc0a3ba3b8637c7357ab65c58fbf
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-creating-a-dataflow-pipeline"></a><span data-ttu-id="fbd3c-102">演练：创建数据流管道</span><span class="sxs-lookup"><span data-stu-id="fbd3c-102">Walkthrough: Creating a Dataflow Pipeline</span></span>
<span data-ttu-id="fbd3c-103">尽管可以使用<xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A?displayProperty=nameWithType>， <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A?displayProperty=nameWithType>，和<xref:System.Threading.Tasks.Dataflow.DataflowBlock.TryReceive%2A?displayProperty=nameWithType>方法来接收来自消息源块，也可以连接消息块来形成*数据流管道*。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-103">Although you can use the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Receive%2A?displayProperty=nameWithType>, <xref:System.Threading.Tasks.Dataflow.DataflowBlock.ReceiveAsync%2A?displayProperty=nameWithType>, and <xref:System.Threading.Tasks.Dataflow.DataflowBlock.TryReceive%2A?displayProperty=nameWithType> methods to receive messages from source blocks, you can also connect message blocks to form a *dataflow pipeline*.</span></span> <span data-ttu-id="fbd3c-104">数据流管道是一系列的组件，或*数据流块*，其中每个执行一个参与更大目标的特定任务。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-104">A dataflow pipeline is a series of components, or *dataflow blocks*, each of which performs a specific task that contributes to a larger goal.</span></span> <span data-ttu-id="fbd3c-105">数据流管道中的每个数据流块会在收到来自另一数据流块的消息时执行工作。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-105">Every dataflow block in a dataflow pipeline performs work when it receives a message from another dataflow block.</span></span> <span data-ttu-id="fbd3c-106">这就好比是汽车制造装配线。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-106">An analogy to this is an assembly line for automobile manufacturing.</span></span> <span data-ttu-id="fbd3c-107">每辆汽车通过装配线时，一站组装车架，下一站则安装引擎，以此类推。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-107">As each vehicle passes through the assembly line, one station assembles the frame, the next one installs the engine, and so on.</span></span> <span data-ttu-id="fbd3c-108">因为装配线可以同时装配多辆汽车，所以比一次装配整辆车拥有更高的产出。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-108">Because an assembly line enables multiple vehicles to be assembled at the same time, it provides better throughput than assembling complete vehicles one at a time.</span></span>  
  
> [!TIP]
>  <span data-ttu-id="fbd3c-109">TPL 数据流库（<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> 命名空间）不是随 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 一起分发的。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-109">The TPL Dataflow Library (<xref:System.Threading.Tasks.Dataflow?displayProperty=nameWithType> namespace) is not distributed with the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span> <span data-ttu-id="fbd3c-110">若要安装<xref:System.Threading.Tasks.Dataflow>命名空间中，打开你的项目中[!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)]，选择**管理 NuGet 包**从项目菜单，然后联机搜索`Microsoft.Tpl.Dataflow`包。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-110">To install the <xref:System.Threading.Tasks.Dataflow> namespace, open your project in [!INCLUDE[vs_dev11_long](../../../includes/vs-dev11-long-md.md)], choose **Manage NuGet Packages** from the Project menu, and search online for the `Microsoft.Tpl.Dataflow` package.</span></span>  
  
 <span data-ttu-id="fbd3c-111">本文档演示下载书籍的数据流管道*Iliad of Homer*从网站和搜索文本匹配单个单词与该相反单词的第一个单词字符。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-111">This document demonstrates a dataflow pipeline that downloads the book *The Iliad of Homer* from a website and searches the text to match individual words with words that reverse the first word's characters.</span></span> <span data-ttu-id="fbd3c-112">本文档中数据流管道的形成包括以下步骤：</span><span class="sxs-lookup"><span data-stu-id="fbd3c-112">The formation of the dataflow pipeline in this document consists of the following steps:</span></span>  
  
1.  <span data-ttu-id="fbd3c-113">创建参与管道的数据流块。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-113">Create the dataflow blocks that participate in the pipeline.</span></span>  
  
2.  <span data-ttu-id="fbd3c-114">连接每个数据流块与管道中的下一个块。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-114">Connect each dataflow block to the next block in the pipeline.</span></span> <span data-ttu-id="fbd3c-115">每个块将管道中前一个块的输出作为输入接收。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-115">Each block receives as input the output of the previous block in the pipeline.</span></span>  
  
3.  <span data-ttu-id="fbd3c-116">对每个数据流块，创建一个延续任务，该延续任务在上一个块完成后将下一个块的状态设置为已完成状态。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-116">For each dataflow block, create a continuation task that sets the next block to the completed state after the previous block finishes.</span></span>  
  
4.  <span data-ttu-id="fbd3c-117">将数据发布到管道的开头。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-117">Post data to the head of the pipeline.</span></span>  
  
5.  <span data-ttu-id="fbd3c-118">将管道的开头标记为已完成。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-118">Mark the head of the pipeline as completed.</span></span>  
  
6.  <span data-ttu-id="fbd3c-119">等待管道完成所有工作。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-119">Wait for the pipeline to complete all work.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="fbd3c-120">先决条件</span><span class="sxs-lookup"><span data-stu-id="fbd3c-120">Prerequisites</span></span>  
 <span data-ttu-id="fbd3c-121">开始本演练之前，请阅读[数据流](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-121">Read [Dataflow](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md) before you start this walkthrough.</span></span>  
  
## <a name="creating-a-console-application"></a><span data-ttu-id="fbd3c-122">创建控制台应用程序</span><span class="sxs-lookup"><span data-stu-id="fbd3c-122">Creating a Console Application</span></span>  
 <span data-ttu-id="fbd3c-123">在 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)] 中，创建一个 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] 或 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] 控制台应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-123">In [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], create a [!INCLUDE[csprcs](../../../includes/csprcs-md.md)] or [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)] Console Application project.</span></span> <span data-ttu-id="fbd3c-124">添加对 System.Threading.Tasks.Dataflow.dll 的引用。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-124">Add a reference to System.Threading.Tasks.Dataflow.dll.</span></span>  
  
 <span data-ttu-id="fbd3c-125">或者，创建一个文件并将其命名为`ReverseWords.cs`(`ReverseWords.vb`为[!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)])，然后在 Visual Studio 命令提示符窗口以编译该项目中运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-125">Alternatively, create a file and name it `ReverseWords.cs` (`ReverseWords.vb` for [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]), and then run the following command in a Visual Studio Command Prompt window to compile the project.</span></span>  
  
 [!INCLUDE[csprcs](../../../includes/csprcs-md.md)]  
  
 <span data-ttu-id="fbd3c-126">**csc.exe /r:System.Threading.Tasks.Dataflow.dll ReverseWords.cs**</span><span class="sxs-lookup"><span data-stu-id="fbd3c-126">**csc.exe /r:System.Threading.Tasks.Dataflow.dll ReverseWords.cs**</span></span>  
  
 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]  
  
 <span data-ttu-id="fbd3c-127">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll ReverseWords.vb**</span><span class="sxs-lookup"><span data-stu-id="fbd3c-127">**vbc.exe /r:System.Threading.Tasks.Dataflow.dll ReverseWords.vb**</span></span>  
  
 <span data-ttu-id="fbd3c-128">将以下代码添加到项目中以创建基本应用程序。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-128">Add the following code to your project to create the basic application.</span></span>  
  
 [!code-csharp[TPLDataflow_Palindromes#2](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#2)]
 [!code-vb[TPLDataflow_Palindromes#2](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#2)]  
  
## <a name="creating-the-dataflow-blocks"></a><span data-ttu-id="fbd3c-129">创建数据流块</span><span class="sxs-lookup"><span data-stu-id="fbd3c-129">Creating the Dataflow Blocks</span></span>  
 <span data-ttu-id="fbd3c-130">将以下代码添加到 `Main` 方法以创建参与管道的数据流块。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-130">Add the following code to the `Main` method to create the dataflow blocks that participate in the pipeline.</span></span> <span data-ttu-id="fbd3c-131">下表总结了管道的每个成员的角色。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-131">The table that follows summarizes the role of each member of the pipeline.</span></span>  
  
 [!code-csharp[TPLDataflow_Palindromes#3](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#3)]
 [!code-vb[TPLDataflow_Palindromes#3](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#3)]  
  
|<span data-ttu-id="fbd3c-132">成员</span><span class="sxs-lookup"><span data-stu-id="fbd3c-132">Member</span></span>|<span data-ttu-id="fbd3c-133">类型</span><span class="sxs-lookup"><span data-stu-id="fbd3c-133">Type</span></span>|<span data-ttu-id="fbd3c-134">描述</span><span class="sxs-lookup"><span data-stu-id="fbd3c-134">Description</span></span>|  
|------------|----------|-----------------|  
|`downloadString`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|<span data-ttu-id="fbd3c-135">从 Web 下载该书的文本。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-135">Downloads the book text from the Web.</span></span>|  
|`createWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|<span data-ttu-id="fbd3c-136">将该书的文本分成单词的数组。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-136">Separates the book text into an array of words.</span></span>|  
|`filterWordList`|<xref:System.Threading.Tasks.Dataflow.TransformBlock%602>|<span data-ttu-id="fbd3c-137">将短单词从单词数组中移除，按字母顺序对得到的单词排序，并删除重复项。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-137">Removes short words from the word array, orders the resulting words alphabetically, and remove duplicates.</span></span>|  
|`findReversedWords`|<xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602>|<span data-ttu-id="fbd3c-138">查找经过筛选的单词数组集合中所有将字母反转后仍在单词数组中出现的单词。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-138">Finds all words in the filtered word array collection whose reverse also occurs in the word array.</span></span>|  
|`printReversedWords`|<xref:System.Threading.Tasks.Dataflow.ActionBlock%601>|<span data-ttu-id="fbd3c-139">向控制台显示单词及对应的倒序词。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-139">Displays words and the corresponding reverse words to the console.</span></span>|  
  
 <span data-ttu-id="fbd3c-140">虽然可以将本示例中数据流管道的多个步骤合并为一个步骤，不过本示例阐释了组合多个独立数据流任务来执行较大任务的概念。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-140">Although you could combine multiple steps in the dataflow pipeline in this example into one step, the example illustrates the concept of composing multiple independent dataflow tasks to perform a larger task.</span></span> <span data-ttu-id="fbd3c-141">示例通过使用 <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> 使管道的每个成员能对其输入数据执行操作并将结果发送到管道中的下一步骤。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-141">The example uses <xref:System.Threading.Tasks.Dataflow.TransformBlock%602> to enable each member of the pipeline to perform an operation on its input data and send the results to the next step in the pipeline.</span></span> <span data-ttu-id="fbd3c-142">管道的 `findReversedWords` 成员是一个 <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> 对象，因为该成员会为每个输入生成多个独立输出。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-142">The `findReversedWords` member of the pipeline is a <xref:System.Threading.Tasks.Dataflow.TransformManyBlock%602> object because it produces multiple independent outputs for each input.</span></span> <span data-ttu-id="fbd3c-143">管道的结尾 `printReversedWords` 是一个 <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> 对象，因为它会对其输入执行一个动作，但不产生结果。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-143">The tail of the pipeline, `printReversedWords`, is a <xref:System.Threading.Tasks.Dataflow.ActionBlock%601> object because it performs an action on its input, and does not produce a result.</span></span>  
  
## <a name="forming-the-pipeline"></a><span data-ttu-id="fbd3c-144">形成管道</span><span class="sxs-lookup"><span data-stu-id="fbd3c-144">Forming the Pipeline</span></span>  
 <span data-ttu-id="fbd3c-145">添加以下代码将每个块与管道中的下一个块连接。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-145">Add the following code to connect each block to the next block in the pipeline.</span></span>  
  
 <span data-ttu-id="fbd3c-146">当您调用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> 方法将源数据流块连接到目标数据流块时，源数据流块会在数据可用时将数据传播到目标块。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-146">When you call the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> method to connect a source dataflow block to a target dataflow block, the source dataflow block propagates data to the target block as data becomes available.</span></span>  
  
 [!code-csharp[TPLDataflow_Palindromes#4](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#4)]
 [!code-vb[TPLDataflow_Palindromes#4](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#4)]  
  
## <a name="creating-the-completion-tasks"></a><span data-ttu-id="fbd3c-147">创建完成任务</span><span class="sxs-lookup"><span data-stu-id="fbd3c-147">Creating the Completion Tasks</span></span>  
 <span data-ttu-id="fbd3c-148">添加以下代码，使每个数据流块能够在处理了所有数据之后执行一个最终操作。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-148">Add the following code to enable each dataflow block to perform a final action after it processes all data.</span></span>  
  
 [!code-csharp[TPLDataflow_Palindromes#5](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#5)]
 [!code-vb[TPLDataflow_Palindromes#5](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#5)]  
  
 <span data-ttu-id="fbd3c-149">若要在管道中传播完成，每个完成任务都要将下一数据流块设为已完成状态。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-149">To propagate completion through the pipeline, each completion task sets the next dataflow block to the completed state.</span></span> <span data-ttu-id="fbd3c-150">例如，当管道的开头设置为已完成状态时，它会处理所有剩余的缓冲信息，然后运行其完成任务，将管道的第二个成员设置为已完成状态。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-150">For example, when the head of the pipeline is set to the completed state, it processes any remaining buffered messages and then runs its completion task, which sets the second member of the pipeline to the completed state.</span></span> <span data-ttu-id="fbd3c-151">管道的第二个成员反过来处理所有剩余的缓冲信息，然后运行其完成任务，将管道的第三个成员设置为已完成状态。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-151">The second member of the pipeline in turn processes any remaining buffered messages and then runs its completion task, which sets the third member of the pipeline to the completed state.</span></span> <span data-ttu-id="fbd3c-152">此过程将继续，直至管道的所有成员都完成。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-152">This process continues until all members of the pipeline finish.</span></span> <span data-ttu-id="fbd3c-153">此示例使用 `delegate` 关键字（`Function` 中为 [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]）来定义延续任务。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-153">This example uses the `delegate` keyword (`Function` in [!INCLUDE[vbprvb](../../../includes/vbprvb-md.md)]) to define the continuation tasks.</span></span>  
  
## <a name="posting-data-to-the-pipeline"></a><span data-ttu-id="fbd3c-154">将数据发布到管道</span><span class="sxs-lookup"><span data-stu-id="fbd3c-154">Posting Data to the Pipeline</span></span>  
 <span data-ttu-id="fbd3c-155">添加以下代码以书的 URL 发布*Iliad of Homer*到数据流管道的开头。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-155">Add the following code to post the URL of the book *The Iliad of Homer* to the head of the dataflow pipeline.</span></span>  
  
 [!code-csharp[TPLDataflow_Palindromes#6](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#6)]
 [!code-vb[TPLDataflow_Palindromes#6](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#6)]  
  
 <span data-ttu-id="fbd3c-156">此示例使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A?displayProperty=nameWithType> 将数据同步发送到管道的开头。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-156">This example uses <xref:System.Threading.Tasks.Dataflow.DataflowBlock.Post%2A?displayProperty=nameWithType> to synchronously send data to the head of the pipeline.</span></span> <span data-ttu-id="fbd3c-157">在必须将数据异步发送到数据流节点时，请使用 <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-157">Use the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.SendAsync%2A?displayProperty=nameWithType> method when you must asynchronously send data to a dataflow node.</span></span>  
  
## <a name="completing-pipeline-activity"></a><span data-ttu-id="fbd3c-158">完成管道活动</span><span class="sxs-lookup"><span data-stu-id="fbd3c-158">Completing Pipeline Activity</span></span>  
 <span data-ttu-id="fbd3c-159">添加以下代码将管道的开头标记为已完成。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-159">Add the following code to mark the head of the pipeline as completed.</span></span> <span data-ttu-id="fbd3c-160">管道的开头在处理了所有缓冲的消息后运行其延续任务。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-160">The head of the pipeline runs its continuation task after it processes all buffered messages.</span></span> <span data-ttu-id="fbd3c-161">此延续任务在管道中传播已完成状态。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-161">This continuation task propagates the completed state through the pipeline.</span></span>  
  
 [!code-csharp[TPLDataflow_Palindromes#7](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#7)]
 [!code-vb[TPLDataflow_Palindromes#7](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#7)]  
  
 <span data-ttu-id="fbd3c-162">此示例通过要处理的数据流管道发送一个 URL。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-162">This example sends one URL through the dataflow pipeline to be processed.</span></span> <span data-ttu-id="fbd3c-163">如果要通过管道发送多个输入，请在提交了所有输入后调用 <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-163">If you send more than one input through a pipeline, call the <xref:System.Threading.Tasks.Dataflow.IDataflowBlock.Complete%2A?displayProperty=nameWithType> method after you submit all the input.</span></span> <span data-ttu-id="fbd3c-164">如果您的应用程序没有表示数据不再可用或应用程序不必等待管道完成的定义完善的点，则可以忽略此步骤。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-164">You can omit this step if your application has no well-defined point at which data is no longer available or the application does not have to wait for the pipeline to finish.</span></span>  
  
## <a name="waiting-for-the-pipeline-to-finish"></a><span data-ttu-id="fbd3c-165">等待管道完成</span><span class="sxs-lookup"><span data-stu-id="fbd3c-165">Waiting for the Pipeline to Finish</span></span>  
 <span data-ttu-id="fbd3c-166">添加以下代码以等待管道完成。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-166">Add the following code to wait for the pipeline to finish.</span></span> <span data-ttu-id="fbd3c-167">由于本示例使用延续任务来在管道中传播完成，因此当管道的结尾完成时整体操作即已完成。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-167">Because this example uses continuation tasks to propagate completion through the pipeline, the overall operation is finished when the tail of the pipeline finishes.</span></span>  
  
 [!code-csharp[TPLDataflow_Palindromes#8](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#8)]
 [!code-vb[TPLDataflow_Palindromes#8](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#8)]  
  
 <span data-ttu-id="fbd3c-168">可以同时等待任一线程或多个线程的数据流完成。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-168">You can wait for dataflow completion from any thread or from multiple threads at the same time.</span></span>  
  
## <a name="the-complete-example"></a><span data-ttu-id="fbd3c-169">完整示例</span><span class="sxs-lookup"><span data-stu-id="fbd3c-169">The Complete Example</span></span>  
 <span data-ttu-id="fbd3c-170">下面的示例显示此演练的完整代码。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-170">The following example shows the complete code for this walkthrough.</span></span>  
  
 [!code-csharp[TPLDataflow_Palindromes#1](../../../samples/snippets/csharp/VS_Snippets_Misc/tpldataflow_palindromes/cs/dataflowpalindromes.cs#1)]
 [!code-vb[TPLDataflow_Palindromes#1](../../../samples/snippets/visualbasic/VS_Snippets_Misc/tpldataflow_palindromes/vb/dataflowpalindromes.vb#1)]  
  
## <a name="next-steps"></a><span data-ttu-id="fbd3c-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fbd3c-171">Next Steps</span></span>  
 <span data-ttu-id="fbd3c-172">此示例发送一个通过数据流管道处理的 URL。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-172">This example sends one URL to process through the dataflow pipeline.</span></span> <span data-ttu-id="fbd3c-173">如果要通过管道发送多个输入值，可以将并行的形式引入应用程序，这与零件在汽车厂中移动的方式类似。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-173">If you send more than one input value through a pipeline, you can introduce a form of parallelism into your application that resembles how parts might move through an automobile factory.</span></span> <span data-ttu-id="fbd3c-174">当管道的第一个成员将其结果发送给第二个成员时，它可以在第二个成员处理第一个结果时并行处理另一个项。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-174">When the first member of the pipeline sends its result to the second member, it can process another item in parallel as the second member processes the first result.</span></span>  
  
 <span data-ttu-id="fbd3c-175">通过使用数据流管道实现的并行称为*粗粒度的并行*因为它通常由的较少量的较大任务组成。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-175">The parallelism that is achieved by using dataflow pipelines is known as *coarse-grained parallelism* because it typically consists of fewer, larger tasks.</span></span> <span data-ttu-id="fbd3c-176">你还可以使用更*细粒度的并行*较小的短时间运行任务中数据流管道。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-176">You can also use a more *fine-grained parallelism* of smaller, short-running tasks in a dataflow pipeline.</span></span> <span data-ttu-id="fbd3c-177">在本示例中，管道的 `findReversedWords` 成员使用 <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> 方法来并行处理工作列表中的多个项。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-177">In this example, the `findReversedWords` member of the pipeline uses the <xref:System.Threading.Tasks.Parallel.ForEach%2A?displayProperty=nameWithType> method to process multiple items in the work list in parallel.</span></span> <span data-ttu-id="fbd3c-178">在粗粒度的管道中使用细粒度并行可以提高总吞吐量。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-178">The use of fine-grained parallelism in a coarse-grained pipeline can improve overall throughput.</span></span>  
  
 <span data-ttu-id="fbd3c-179">此外可以将源数据流块连接到多个目标块以创建*数据流网络*。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-179">You can also connect a source dataflow block to multiple target blocks to create a *dataflow network*.</span></span> <span data-ttu-id="fbd3c-180"><xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> 方法采用一个 <xref:System.Predicate%601> 对象，该对象定义了目标块是否根据其值来接受每个消息。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-180">The overloaded version of the <xref:System.Threading.Tasks.Dataflow.DataflowBlock.LinkTo%2A> method takes a <xref:System.Predicate%601> object that defines whether the target block accepts each message based on its value.</span></span> <span data-ttu-id="fbd3c-181">大多数充当源的数据流块类型按目标块连接的顺序向所有已连接的目标块提供消息，直到其中一个块接受此消息。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-181">Most dataflow block types that act as sources offer messages to all connected target blocks, in the order in which they were connected, until one of the blocks accepts that message.</span></span> <span data-ttu-id="fbd3c-182">通过使用此筛选机制，您可以创建已连接数据流块的系统，指示某些数据通过一条路径，其他数据通过另一条路径。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-182">By using this filtering mechanism, you can create systems of connected dataflow blocks that direct certain data through one path and other data through another path.</span></span> <span data-ttu-id="fbd3c-183">有关使用筛选创建数据流网络的示例，请参阅[演练： 在 Windows 窗体应用程序中使用数据流](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md)。</span><span class="sxs-lookup"><span data-stu-id="fbd3c-183">For an example that uses filtering to create a dataflow network, see [Walkthrough: Using Dataflow in a Windows Forms Application](../../../docs/standard/parallel-programming/walkthrough-using-dataflow-in-a-windows-forms-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbd3c-184">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fbd3c-184">See Also</span></span>  
 [<span data-ttu-id="fbd3c-185">数据流</span><span class="sxs-lookup"><span data-stu-id="fbd3c-185">Dataflow</span></span>](../../../docs/standard/parallel-programming/dataflow-task-parallel-library.md)
