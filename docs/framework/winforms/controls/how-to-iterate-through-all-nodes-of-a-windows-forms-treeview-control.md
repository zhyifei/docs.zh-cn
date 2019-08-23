---
title: 如何：循环访问 Windows 窗体 TreeView 控件的所有节点
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- TreeView control [Windows Forms], iterating through nodes
- tree nodes in TreeView control [Windows Forms], iterating through
ms.assetid: 427f8928-ebcf-4beb-887f-695b905d5134
ms.openlocfilehash: 00a0f19803967f02795e3eade767786eecc1f4dd
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966547"
---
# <a name="how-to-iterate-through-all-nodes-of-a-windows-forms-treeview-control"></a><span data-ttu-id="5f095-102">如何：循环访问 Windows 窗体 TreeView 控件的所有节点</span><span class="sxs-lookup"><span data-stu-id="5f095-102">How to: Iterate Through All Nodes of a Windows Forms TreeView Control</span></span>
<span data-ttu-id="5f095-103">检查 Windows 窗体<xref:System.Windows.Forms.TreeView>控件中的每个节点有时很有用, 以便对节点值执行某些计算。</span><span class="sxs-lookup"><span data-stu-id="5f095-103">It is sometimes useful to examine every node in a Windows Forms <xref:System.Windows.Forms.TreeView> control in order to perform some calculation on the node values.</span></span> <span data-ttu-id="5f095-104">使用循环访问每个树集合中每个节点的递归过程（C# 和 C++ 中为递归方法）可完成此操作。</span><span class="sxs-lookup"><span data-stu-id="5f095-104">This operation can be done using a recursive procedure (recursive method in C# and C++) that iterates through each node in each collection of the tree.</span></span>  
  
 <span data-ttu-id="5f095-105">树<xref:System.Windows.Forms.TreeNode>视图中的每个对象都具有可用于在树视图中导航的属性<xref:System.Windows.Forms.TreeNode.FirstNode%2A>: <xref:System.Windows.Forms.TreeNode.LastNode%2A>、 <xref:System.Windows.Forms.TreeNode.NextNode%2A>、 <xref:System.Windows.Forms.TreeNode.PrevNode%2A>、和<xref:System.Windows.Forms.TreeNode.Parent%2A>。</span><span class="sxs-lookup"><span data-stu-id="5f095-105">Each <xref:System.Windows.Forms.TreeNode> object in a tree view has properties that you can use to navigate the tree view: <xref:System.Windows.Forms.TreeNode.FirstNode%2A>, <xref:System.Windows.Forms.TreeNode.LastNode%2A>, <xref:System.Windows.Forms.TreeNode.NextNode%2A>, <xref:System.Windows.Forms.TreeNode.PrevNode%2A>, and <xref:System.Windows.Forms.TreeNode.Parent%2A>.</span></span> <span data-ttu-id="5f095-106"><xref:System.Windows.Forms.TreeNode.Parent%2A>属性的值为当前节点的父节点。</span><span class="sxs-lookup"><span data-stu-id="5f095-106">The value of the <xref:System.Windows.Forms.TreeNode.Parent%2A> property is the parent node of the current node.</span></span> <span data-ttu-id="5f095-107">当前节点的子节点 (如果有) 将在其<xref:System.Windows.Forms.TreeNode.Nodes%2A>属性中列出。</span><span class="sxs-lookup"><span data-stu-id="5f095-107">The child nodes of the current node, if there are any, are listed in its <xref:System.Windows.Forms.TreeNode.Nodes%2A> property.</span></span> <span data-ttu-id="5f095-108"><xref:System.Windows.Forms.TreeView>控件本身<xref:System.Windows.Forms.TreeView.TopNode%2A>具有属性, 该属性是整个树视图的根节点。</span><span class="sxs-lookup"><span data-stu-id="5f095-108">The <xref:System.Windows.Forms.TreeView> control itself has the <xref:System.Windows.Forms.TreeView.TopNode%2A> property, which is the root node of the entire tree view.</span></span>  
  
### <a name="to-iterate-through-all-nodes-of-the-treeview-control"></a><span data-ttu-id="5f095-109">循环访问 TreeView 控件的所有节点</span><span class="sxs-lookup"><span data-stu-id="5f095-109">To iterate through all nodes of the TreeView control</span></span>  
  
1. <span data-ttu-id="5f095-110">创建测试每个节点的递归过程（C# 和 C++ 中为递归方法）。</span><span class="sxs-lookup"><span data-stu-id="5f095-110">Create a recursive procedure (recursive method in C# and C++) that tests each node.</span></span>  
  
2. <span data-ttu-id="5f095-111">调用过程。</span><span class="sxs-lookup"><span data-stu-id="5f095-111">Call the procedure.</span></span>  
  
     <span data-ttu-id="5f095-112">下面的示例演示如何打印每个<xref:System.Windows.Forms.TreeNode>对象的<xref:System.Windows.Forms.TreeNode.Text%2A>属性:</span><span class="sxs-lookup"><span data-stu-id="5f095-112">The following example shows how to print each <xref:System.Windows.Forms.TreeNode> object's <xref:System.Windows.Forms.TreeNode.Text%2A> property:</span></span>  
  
    ```vb  
    Private Sub PrintRecursive(ByVal n As TreeNode)  
       System.Diagnostics.Debug.WriteLine(n.Text)  
       MessageBox.Show(n.Text)  
       Dim aNode As TreeNode  
       For Each aNode In n.Nodes  
          PrintRecursive(aNode)  
       Next  
    End Sub  
  
    ' Call the procedure using the top nodes of the treeview.  
    Private Sub CallRecursive(ByVal aTreeView As TreeView)  
       Dim n As TreeNode  
       For Each n In aTreeView.Nodes  
          PrintRecursive(n)  
       Next  
    End Sub  
    ```  
  
    ```csharp  
    private void PrintRecursive(TreeNode treeNode)  
    {  
       // Print the node.  
       System.Diagnostics.Debug.WriteLine(treeNode.Text);  
       MessageBox.Show(treeNode.Text);  
       // Print each node recursively.  
       foreach (TreeNode tn in treeNode.Nodes)  
       {  
          PrintRecursive(tn);  
       }  
    }  
  
    // Call the procedure using the TreeView.  
    private void CallRecursive(TreeView treeView)  
    {  
       // Print each node recursively.  
       TreeNodeCollection nodes = treeView.Nodes;  
       foreach (TreeNode n in nodes)  
       {  
          PrintRecursive(n);  
       }  
    }  
    ```  
  
    ```cpp  
    private:  
       void PrintRecursive( TreeNode^ treeNode )  
       {  
          // Print the node.  
          System::Diagnostics::Debug::WriteLine( treeNode->Text );  
          MessageBox::Show( treeNode->Text );  
  
          // Print each node recursively.  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(treeNode->Nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ tn = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( tn );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
  
       // Call the procedure using the TreeView.  
       void CallRecursive( TreeView^ treeView )  
       {  
          // Print each node recursively.  
          TreeNodeCollection^ nodes = treeView->Nodes;  
          System::Collections::IEnumerator^ myNodes = (safe_cast<System::Collections::IEnumerable^>(nodes))->GetEnumerator();  
          try  
          {  
             while ( myNodes->MoveNext() )  
             {  
                TreeNode^ n = safe_cast<TreeNode^>(myNodes->Current);  
                PrintRecursive( n );  
             }  
          }  
          finally  
          {  
             IDisposable^ disposable = dynamic_cast<System::IDisposable^>(myNodes);  
             if ( disposable != nullptr )  
                      disposable->Dispose();  
          }  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="5f095-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5f095-113">See also</span></span>

- [<span data-ttu-id="5f095-114">TreeView 控件</span><span class="sxs-lookup"><span data-stu-id="5f095-114">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="5f095-115">递归过程</span><span class="sxs-lookup"><span data-stu-id="5f095-115">Recursive Procedures</span></span>](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md)
