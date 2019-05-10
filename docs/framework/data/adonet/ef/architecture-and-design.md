---
title: 体系结构和设计
ms.date: 03/30/2017
ms.assetid: bd738d39-00e2-4bab-b387-90aac1a014bd
ms.openlocfilehash: 20edf6e2546830fd9fa764a2936987c573b8283a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64632032"
---
# <a name="architecture-and-design"></a><span data-ttu-id="46d32-102">体系结构和设计</span><span class="sxs-lookup"><span data-stu-id="46d32-102">Architecture and Design</span></span>
<span data-ttu-id="46d32-103">中的 SQL 生成模块[示例提供程序](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0)作为表示命令目录树的表达式树的访问者实现。</span><span class="sxs-lookup"><span data-stu-id="46d32-103">The SQL generation module in the [Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) is implemented as a visitor on the expression tree that represents the command tree.</span></span> <span data-ttu-id="46d32-104">通过表达式树上的单个传递来执行生成。</span><span class="sxs-lookup"><span data-stu-id="46d32-104">The generation is done in a single pass over the expression tree.</span></span>  
  
 <span data-ttu-id="46d32-105">从下至上处理树中的节点。</span><span class="sxs-lookup"><span data-stu-id="46d32-105">The nodes of the tree are processed from the bottom up.</span></span> <span data-ttu-id="46d32-106">首先，生成中间结构：SqlSelectStatement 或 SqlBuilder，这两个实现 ISqlFragment。</span><span class="sxs-lookup"><span data-stu-id="46d32-106">First, an intermediate structure is produced: SqlSelectStatement or SqlBuilder, both implementing ISqlFragment.</span></span> <span data-ttu-id="46d32-107">紧接着，从该结构生成字符串 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="46d32-107">Next, the string SQL statement is produced from that structure.</span></span> <span data-ttu-id="46d32-108">生成中间结构的原因有两个：</span><span class="sxs-lookup"><span data-stu-id="46d32-108">There are two reasons for the intermediate structure:</span></span>  
  
- <span data-ttu-id="46d32-109">从逻辑上说，不按顺序填充 SQL SELECT 语句。</span><span class="sxs-lookup"><span data-stu-id="46d32-109">Logically, a SQL SELECT statement is populated out of order.</span></span> <span data-ttu-id="46d32-110">先访问参与 FROM 子句的节点，然后再访问参与 WHERE、GROUP BY 和 ORDER BY 子句的节点。</span><span class="sxs-lookup"><span data-stu-id="46d32-110">The nodes that participate in the FROM clause are visited before the nodes that participate in the WHERE, GROUP BY, and the ORDER BY clause.</span></span>  
  
- <span data-ttu-id="46d32-111">若要重命名别名，您必须标识所有使用的别名，避免在重命名期间发生冲突。</span><span class="sxs-lookup"><span data-stu-id="46d32-111">To rename aliases, you must identify all used aliases to avoid collisions during renaming.</span></span> <span data-ttu-id="46d32-112">若要延迟 SqlBuilder 中的重命名选择，请使用 Symbol 对象以表示作为重命名候选项的列。</span><span class="sxs-lookup"><span data-stu-id="46d32-112">To defer the renaming choices in SqlBuilder, use Symbol objects to represent the columns that are candidates for renaming.</span></span>  
  
 <span data-ttu-id="46d32-113">![Diagram](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span><span class="sxs-lookup"><span data-stu-id="46d32-113">![Diagram](../../../../../docs/framework/data/adonet/ef/media/de1ca705-4f7c-4d2d-ace5-afefc6d3cefa.gif "de1ca705-4f7c-4d2d-ace5-afefc6d3cefa")</span></span>  
  
 <span data-ttu-id="46d32-114">在第一阶段，当访问表达式树时，将表达式组合为 SqlSelectStatements，对联接进行平展并对联接别名进行平展。</span><span class="sxs-lookup"><span data-stu-id="46d32-114">In the first phase, while visiting the expression tree, expressions are grouped into SqlSelectStatements, joins are flattened, and join aliases are flattened.</span></span> <span data-ttu-id="46d32-115">在此传递过程中，Symbol 对象表示可以重命名的列或输入别名。</span><span class="sxs-lookup"><span data-stu-id="46d32-115">During this pass, Symbol objects represent columns or input aliases that may be renamed.</span></span>  
  
 <span data-ttu-id="46d32-116">在第二阶段，当生成实际字符串时，将重命名别名。</span><span class="sxs-lookup"><span data-stu-id="46d32-116">In the second phase, while producing the actual string, aliases are renamed.</span></span>  
  
## <a name="data-structures"></a><span data-ttu-id="46d32-117">数据结构</span><span class="sxs-lookup"><span data-stu-id="46d32-117">Data Structures</span></span>  
 <span data-ttu-id="46d32-118">本部分讨论中使用的类型[示例提供程序](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0)用于生成 SQL 语句。</span><span class="sxs-lookup"><span data-stu-id="46d32-118">This section discusses the types used in the [Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) that you use to build a SQL statement.</span></span>  
  
### <a name="isqlfragment"></a><span data-ttu-id="46d32-119">ISqlFragment</span><span class="sxs-lookup"><span data-stu-id="46d32-119">ISqlFragment</span></span>  
 <span data-ttu-id="46d32-120">本节涵盖实现 ISqlFragment 接口的类，此接口有两个用途：</span><span class="sxs-lookup"><span data-stu-id="46d32-120">This section covers the classes that implement the ISqlFragment interface, which serves two purposes:</span></span>  
  
- <span data-ttu-id="46d32-121">所有访问者方法的常见返回类型。</span><span class="sxs-lookup"><span data-stu-id="46d32-121">A common return type for all the visitor methods.</span></span>  
  
- <span data-ttu-id="46d32-122">提供用于写入最终 SQL 字符串的方法。</span><span class="sxs-lookup"><span data-stu-id="46d32-122">Gives a method to write the final SQL string.</span></span>  
  
```  
internal interface ISqlFragment {  
   void WriteSql(SqlWriter writer, SqlGenerator sqlGenerator);  
}  
```  
  
#### <a name="sqlbuilder"></a><span data-ttu-id="46d32-123">SqlBuilder</span><span class="sxs-lookup"><span data-stu-id="46d32-123">SqlBuilder</span></span>  
 <span data-ttu-id="46d32-124">SqlBuilder 是针对最终 SQL 字符串的收集设备（与 StringBuilder 类似）。</span><span class="sxs-lookup"><span data-stu-id="46d32-124">SqlBuilder is a gathering device for the final SQL string, similar to StringBuilder.</span></span> <span data-ttu-id="46d32-125">它包含构成最终 SQL 的字符串与可转换为字符串的 ISqlFragment。</span><span class="sxs-lookup"><span data-stu-id="46d32-125">It consists of the strings that make up the final SQL, along with ISqlFragments that can be converted into strings.</span></span>  
  
```  
internal sealed class SqlBuilder : ISqlFragment {  
   public void Append(object s)  
   public void AppendLine()  
   public bool IsEmpty  
}  
```  
  
#### <a name="sqlselectstatement"></a><span data-ttu-id="46d32-126">SqlSelectStatement</span><span class="sxs-lookup"><span data-stu-id="46d32-126">SqlSelectStatement</span></span>  
 <span data-ttu-id="46d32-127">SqlSelectStatement 表示形状"SELECT...的规范 SQL SELECT 语句</span><span class="sxs-lookup"><span data-stu-id="46d32-127">SqlSelectStatement represents a canonical SQL SELECT statement of the shape "SELECT …</span></span> <span data-ttu-id="46d32-128">从。</span><span class="sxs-lookup"><span data-stu-id="46d32-128">FROM  ..</span></span> <span data-ttu-id="46d32-129">WHERE...</span><span class="sxs-lookup"><span data-stu-id="46d32-129">WHERE …</span></span> <span data-ttu-id="46d32-130">分组依据...</span><span class="sxs-lookup"><span data-stu-id="46d32-130">GROUP BY …</span></span> <span data-ttu-id="46d32-131">ORDER BY"。</span><span class="sxs-lookup"><span data-stu-id="46d32-131">ORDER BY".</span></span>  
  
 <span data-ttu-id="46d32-132">每个 SQL 子句均由一个 StringBuilder 表示。</span><span class="sxs-lookup"><span data-stu-id="46d32-132">Each of the SQL clauses is represented by a StringBuilder.</span></span> <span data-ttu-id="46d32-133">此外，它跟踪是否已指定 Distinct 以及语句是否位于最顶层。</span><span class="sxs-lookup"><span data-stu-id="46d32-133">In addition, it tracks whether Distinct has been specified and whether the statement is topmost.</span></span> <span data-ttu-id="46d32-134">如果语句未位于最顶层，则除非语句也具有 TOP 子句，否则将忽略 ORDER BY 子句。</span><span class="sxs-lookup"><span data-stu-id="46d32-134">If the statement is not topmost, the ORDER BY clause is omitted unless the statement also has a TOP clause.</span></span>  
  
 <span data-ttu-id="46d32-135">FromExtents 包含 SELECT 语句的查询的列表。</span><span class="sxs-lookup"><span data-stu-id="46d32-135">FromExtents contains the list of inputs for the SELECT statement.</span></span> <span data-ttu-id="46d32-136">该语句中通常只有一个元素。</span><span class="sxs-lookup"><span data-stu-id="46d32-136">There is usually just one element in this.</span></span> <span data-ttu-id="46d32-137">联接的 SELECT 语句可以暂时具有多个元素。</span><span class="sxs-lookup"><span data-stu-id="46d32-137">SELECT statements for joins may temporarily have more than one element.</span></span>  
  
 <span data-ttu-id="46d32-138">如果 SELECT 语句是由 Join 节点创建的，则 SqlSelectStatement 将保留已在 AllJoinExtents 的联接中平展的所有范围的列表。</span><span class="sxs-lookup"><span data-stu-id="46d32-138">If the SELECT statement is created by a Join node, SqlSelectStatement maintains a list of all the extents that have been flattened in the join in AllJoinExtents.</span></span> <span data-ttu-id="46d32-139">OuterExtents 表示 SqlSelectStatement 的外部引用并用于输入别名重命名。</span><span class="sxs-lookup"><span data-stu-id="46d32-139">OuterExtents represents outer references of the SqlSelectStatement and is used for input alias renaming.</span></span>  
  
```  
internal sealed class SqlSelectStatement : ISqlFragment {  
   internal bool IsDistinct { get, set };  
   internal bool IsTopMost  
  
   internal List<Symbol> AllJoinExtents { get, set };  
   internal List<Symbol> FromExtents { get};  
   internal Dictionary<Symbol, bool> OuterExtents { get};  
  
   internal TopClause Top { get, set };  
  
   internal SqlBuilder Select {get};  
   internal SqlBuilder From  
   internal SqlBuilder Where  
   internal SqlBuilder GroupBy  
   public SqlBuilder OrderBy  
}  
```  
  
#### <a name="topclause"></a><span data-ttu-id="46d32-140">TopClause</span><span class="sxs-lookup"><span data-stu-id="46d32-140">TopClause</span></span>  
 <span data-ttu-id="46d32-141">TopClause 表示 SqlSelectStatement 中的 TOP 表达式。</span><span class="sxs-lookup"><span data-stu-id="46d32-141">TopClause represents the TOP expression in a SqlSelectStatement.</span></span> <span data-ttu-id="46d32-142">TopCount 属性指示应选择的 TOP 行的数目。</span><span class="sxs-lookup"><span data-stu-id="46d32-142">The TopCount property indicates how many TOP rows should be selected.</span></span>  <span data-ttu-id="46d32-143">当 WithTies 为 true 时，指示已从 DbLimitExpession 构建 TopClause。</span><span class="sxs-lookup"><span data-stu-id="46d32-143">When WithTies is true, the TopClause was built from a DbLimitExpession.</span></span>  
  
```  
class TopClause : ISqlFragment {  
   internal bool WithTies {get}  
   internal ISqlFragment TopCount {get}  
   internal TopClause(ISqlFragment topCount, bool withTies)  
   internal TopClause(int topCount, bool withTies)  
}  
```  
  
### <a name="symbols"></a><span data-ttu-id="46d32-144">Symbols</span><span class="sxs-lookup"><span data-stu-id="46d32-144">Symbols</span></span>  
 <span data-ttu-id="46d32-145">与符号相关的类和符号表将执行输入别名重命名、联接别名平展和列别名重命名。</span><span class="sxs-lookup"><span data-stu-id="46d32-145">The Symbol-related classes and the symbol table perform input alias renaming, join alias flattening, and column alias renaming.</span></span>  
  
 <span data-ttu-id="46d32-146">Symbol 类表示范围、嵌套 SELECT 语句或列。</span><span class="sxs-lookup"><span data-stu-id="46d32-146">The Symbol class represents an extent, a nested SELECT statement, or a column.</span></span> <span data-ttu-id="46d32-147">使用符号代替实际别名可在使用符号之后进行重命名，并且符号还带有它表示的项目（如类型）的其他信息。</span><span class="sxs-lookup"><span data-stu-id="46d32-147">It is used instead of an actual alias to allow for renaming after it has been used and it also carries additional information for the artifact it represents (like the type).</span></span>  
  
```  
class Symbol : ISqlFragment {  
   internal Dictionary<string, Symbol> Columns {get}  
   internal bool NeedsRenaming {get, set}  
   internal bool IsUnnest {get, set}   //not used  
  
   public string Name{get}  
   public string NewName {get,set}  
   internal TypeUsage Type {get, set}  
  
   public Symbol(string name, TypeUsage type)  
}  
```  
  
 <span data-ttu-id="46d32-148">Name 存储表示的范围、嵌套 SELECT 语句或列的原始别名。</span><span class="sxs-lookup"><span data-stu-id="46d32-148">Name stores the original alias for the represented extent, nested SELECT statement, or a column.</span></span>  
  
 <span data-ttu-id="46d32-149">NewName 存储 SQL SELECT 语句中将使用的别名。</span><span class="sxs-lookup"><span data-stu-id="46d32-149">NewName stores the alias that will be used in the SQL SELECT statement.</span></span> <span data-ttu-id="46d32-150">最初将设置为 Name，仅在生成最终字符串查询时根据需要进行重命名。</span><span class="sxs-lookup"><span data-stu-id="46d32-150">It is originally set to Name, and only renamed if needed when generating the final string query.</span></span>  
  
 <span data-ttu-id="46d32-151">Type 仅对表示范围和嵌套 SELECT 语句的符号有用。</span><span class="sxs-lookup"><span data-stu-id="46d32-151">Type is only useful for symbols representing extents and nested SELECT statements.</span></span>  
  
#### <a name="symbolpair"></a><span data-ttu-id="46d32-152">SymbolPair</span><span class="sxs-lookup"><span data-stu-id="46d32-152">SymbolPair</span></span>  
 <span data-ttu-id="46d32-153">SymbolPair 类对记录平展进行寻址。</span><span class="sxs-lookup"><span data-stu-id="46d32-153">The SymbolPair class addresses record flattening.</span></span>  
  
 <span data-ttu-id="46d32-154">考虑属性表达式 D(v, "j3.j2.j1.a.x")，其中 v 是 VarRef，j1、j2、j3 为联接，a 为范围，而 x 为列。</span><span class="sxs-lookup"><span data-stu-id="46d32-154">Consider a property expression D(v, "j3.j2.j1.a.x") where v is a VarRef, j1, j2, j3 are joins, a is an extent, and x is a columns.</span></span>  
  
 <span data-ttu-id="46d32-155">最后必须将其转换为 {j'}.{x'}。</span><span class="sxs-lookup"><span data-stu-id="46d32-155">This has to be translated eventually into {j'}.{x'}.</span></span> <span data-ttu-id="46d32-156">源字段表示最外部的 SqlStatement，它表示联接表达式（例如 j2）；这始终是一个联接符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-156">The source field represents the outermost SqlStatement, representing a join expression (say j2); this is always a Join symbol.</span></span> <span data-ttu-id="46d32-157">列字段从一个联接符号移动到下一个联接符号，直到它停止在一个非联接符号处。</span><span class="sxs-lookup"><span data-stu-id="46d32-157">The column field moves from one join symbol to the next until it stops at a non-join symbol.</span></span> <span data-ttu-id="46d32-158">这将在访问 DbPropertyExpression 时返回，但绝不会添加到 SqlBuilder。</span><span class="sxs-lookup"><span data-stu-id="46d32-158">This is returned when visiting a DbPropertyExpression but is never added to a SqlBuilder.</span></span>  
  
```  
class SymbolPair : ISqlFragment {  
   public Symbol Source;  
   public Symbol Column;  
   public SymbolPair(Symbol source, Symbol column)  
}  
```  
  
#### <a name="joinsymbol"></a><span data-ttu-id="46d32-159">JoinSymbol</span><span class="sxs-lookup"><span data-stu-id="46d32-159">JoinSymbol</span></span>  
 <span data-ttu-id="46d32-160">联接符号是一个表示带联接或联接输入的嵌套 SELECT 语句的符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-160">A Join symbol is a Symbol that represents a nested SELECT statement with a join or a join input.</span></span>  
  
```  
internal sealed class JoinSymbol : Symbol {  
   internal List<Symbol> ColumnList {get, set}  
   internal List<Symbol> ExtentList {get}  
   internal List<Symbol> FlattenedExtentList {get, set}  
   internal Dictionary<string, Symbol> NameToExtent {get}  
   internal bool IsNestedJoin {get, set}  
  
   public JoinSymbol(string name, TypeUsage type, List<Symbol> extents)  
}  
```  
  
 <span data-ttu-id="46d32-161">ColumnList 表示 SELECT 子句中的列的列表（如果此符号表示 SQL SELECT 语句）。</span><span class="sxs-lookup"><span data-stu-id="46d32-161">ColumnList represents the list of columns in the SELECT clause if this symbol represents a SQL SELECT statement.</span></span> <span data-ttu-id="46d32-162">ExtentList 为 SELECT 子句中的范围的列表。</span><span class="sxs-lookup"><span data-stu-id="46d32-162">ExtentList is the list of extents in the SELECT clause.</span></span> <span data-ttu-id="46d32-163">如果已在顶层平展联接的多个范围，则 FlattenedExtentList 将跟踪这些范围以确保对其别名进行的重命名正确。</span><span class="sxs-lookup"><span data-stu-id="46d32-163">If the join has multiple extents flattened at the top level, FlattenedExtentList tracks the extents to ensure that extent aliases are renamed correctly.</span></span>  
  
 <span data-ttu-id="46d32-164">NameToExtent 将 ExtentList 中的所有范围用作一个字典。</span><span class="sxs-lookup"><span data-stu-id="46d32-164">NameToExtent has all the extents in ExtentList as a dictionary.</span></span> <span data-ttu-id="46d32-165">IsNestedJoin 用于确定 JoinSymbol 是普通的联接符号还是具有相应的 SqlSelectStatement 的联接符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-165">IsNestedJoin is used to determine whether a JoinSymbol is an ordinary join symbol or one that has a corresponding SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="46d32-166">所有列表只设置一次，然后用于查找或枚举。</span><span class="sxs-lookup"><span data-stu-id="46d32-166">All the lists are set exactly once and then used for lookups or enumeration.</span></span>  
  
#### <a name="symboltable"></a><span data-ttu-id="46d32-167">SymbolTable</span><span class="sxs-lookup"><span data-stu-id="46d32-167">SymbolTable</span></span>  
 <span data-ttu-id="46d32-168">SymbolTable 用于将变量名解析为符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-168">SymbolTable is used to resolve variable names to Symbols.</span></span> <span data-ttu-id="46d32-169">SymbolTable 是作为带每个范围的新项的堆栈实现的。</span><span class="sxs-lookup"><span data-stu-id="46d32-169">SymbolTable is implemented as a stack with a new entry for each scope.</span></span> <span data-ttu-id="46d32-170">查找将从上至下搜索堆栈，直到找到一个项。</span><span class="sxs-lookup"><span data-stu-id="46d32-170">Lookups search from the top of the stack to the bottom until an entry is found.</span></span>  
  
```  
internal sealed class SymbolTable {  
   internal void EnterScope()  
   internal void ExitScope()  
   internal void Add(string name, Symbol value)  
   internal Symbol Lookup(string name)  
}  
```  
  
 <span data-ttu-id="46d32-171">一个 Sql 生成模块实例仅有一个 SymbolTable。</span><span class="sxs-lookup"><span data-stu-id="46d32-171">There is only one SymbolTable per one instance of the Sql Generation module.</span></span> <span data-ttu-id="46d32-172">对于每个关系节点都会进入和退出范围。</span><span class="sxs-lookup"><span data-stu-id="46d32-172">Scopes are entered and exited for each relational node.</span></span> <span data-ttu-id="46d32-173">以前的范围中的所有符号对于以后的范围均可见，除非具有同一名称的其他符号将这些范围隐藏。</span><span class="sxs-lookup"><span data-stu-id="46d32-173">All symbols in earlier scopes are visible to later scopes unless hidden by other symbols with the same name.</span></span>  
  
### <a name="global-state-for-the-visitor"></a><span data-ttu-id="46d32-174">访问者的全局状态</span><span class="sxs-lookup"><span data-stu-id="46d32-174">Global State for the Visitor</span></span>  
 <span data-ttu-id="46d32-175">为了帮助重命名别名和列，保留包含所有列名 (AllColumnName) 和范围别名 (AllExtentName) 的列表，在查询树中进行第一次传递时已使用这些别名。</span><span class="sxs-lookup"><span data-stu-id="46d32-175">To assist in renaming of aliases and columns, maintain a list of all the column names (AllColumnNames) and extent aliases (AllExtentNames) that have been used in the first pass over the query tree.</span></span>  <span data-ttu-id="46d32-176">符号表可将变量名解析为符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-176">The symbol table resolves variable names to Symbols.</span></span> <span data-ttu-id="46d32-177">IsVarRefSingle 仅用于验证目的，但它并非绝对必需的。</span><span class="sxs-lookup"><span data-stu-id="46d32-177">IsVarRefSingle is only used for verification purposes, it is not strictly necessary.</span></span>  
  
 <span data-ttu-id="46d32-178">由于访问者模式不允许传递参数，通过 CurrentSelectStatement 和 IsParentAJoin 使用的两个堆栈可用于将“参数”从父节点传递到子节点。</span><span class="sxs-lookup"><span data-stu-id="46d32-178">The two stacks used via CurrentSelectStatement and IsParentAJoin are used to pass "parameters" from parent to child nodes, since the visitor pattern does not allow us to pass parameters.</span></span>  
  
```  
internal Dictionary<string, int> AllExtentNames {get}  
internal Dictionary<string, int> AllColumnNames {get}  
SymbolTable symbolTable = new SymbolTable();  
bool isVarRefSingle = false;  
  
Stack<SqlSelectStatement> selectStatementStack;  
private SqlSelectStatement CurrentSelectStatement{get}  
  
Stack<bool> isParentAJoinStack;  
private bool IsParentAJoin{get}  
```  
  
## <a name="common-scenarios"></a><span data-ttu-id="46d32-179">常见方案</span><span class="sxs-lookup"><span data-stu-id="46d32-179">Common Scenarios</span></span>  
 <span data-ttu-id="46d32-180">本节讨论常见的提供程序方案。</span><span class="sxs-lookup"><span data-stu-id="46d32-180">This section discusses common provider scenarios.</span></span>  
  
### <a name="grouping-expression-nodes-into-sql-statements"></a><span data-ttu-id="46d32-181">将表达式节点组合为 SQL 语句</span><span class="sxs-lookup"><span data-stu-id="46d32-181">Grouping Expression Nodes into SQL Statements</span></span>  
 <span data-ttu-id="46d32-182">若从下往上访问树，则当遇到第一个关系节点（通常为 DbScanExpression 范围）时，将创建 SqlSelectStatement。</span><span class="sxs-lookup"><span data-stu-id="46d32-182">A SqlSelectStatement is created when the first relational node is encountered (typically a DbScanExpression extent) when visiting the tree from the bottom up.</span></span> <span data-ttu-id="46d32-183">若要使用尽可能少的嵌套查询生成 SQL SELECT 语句，请在 SqlSelectStatement 中聚合尽可能多的父节点。</span><span class="sxs-lookup"><span data-stu-id="46d32-183">To produce a SQL SELECT statement with as few nested queries as possible, aggregate as many of its parent nodes as possible in that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="46d32-184">有关是否可将给定的（关系）节点添加到当前的 SqlSelectStatement（访问输入时返回的语句）或是否需要启动新语句的决策，将由方法 IsCompatible 来计算并取决于 SqlSelectStatement 中所含内容（这些内容取决于给定节点下方的节点）。</span><span class="sxs-lookup"><span data-stu-id="46d32-184">The decision of whether a given (relational) node can be added to the current SqlSelectStatement (the one returned when visiting the input) or if a new statement needs to be started is computed by the method IsCompatible and depends on what is already in the SqlSelectStatement, which depends on what nodes were below the given node.</span></span>  
  
 <span data-ttu-id="46d32-185">通常，如果在计算其考虑合并的节点不为空的子句之后再计算 SQL 语句子句，则无法将节点添加到当前语句。</span><span class="sxs-lookup"><span data-stu-id="46d32-185">Typically, if SQL statement clauses are evaluated after clauses where the nodes being considered for merging are not empty, the node cannot be added to the current statement.</span></span> <span data-ttu-id="46d32-186">例如，如果下一个节点为 Filter，则仅在满足以下条件时可将该节点并入当前 SqlSelectStatement 中：</span><span class="sxs-lookup"><span data-stu-id="46d32-186">For example, if the next node is a Filter, that node can be incorporated into the current SqlSelectStatement only if the following is true:</span></span>  
  
- <span data-ttu-id="46d32-187">SELECT 列表为空。</span><span class="sxs-lookup"><span data-stu-id="46d32-187">The SELECT list is empty.</span></span> <span data-ttu-id="46d32-188">如果 SELECT 列表不为空，则表明 select 列表是由 filter 前面的节点生成的，并且谓词可能更愿意使用由该 SELECT 列表生成的列。</span><span class="sxs-lookup"><span data-stu-id="46d32-188">If the SELECT list is not empty, the select list was produced by a node preceding the filter and the predicate may refer to columns produced by that SELECT list.</span></span>  
  
- <span data-ttu-id="46d32-189">GROUPBY 为空。</span><span class="sxs-lookup"><span data-stu-id="46d32-189">The GROUPBY is empty.</span></span> <span data-ttu-id="46d32-190">如果 GROUPBY 不为空，则添加 filter 将表示在分组之前进行筛选，此操作是不正确的。</span><span class="sxs-lookup"><span data-stu-id="46d32-190">If the GROUPBY is not empty, adding the filter would mean filtering before grouping, which is not correct.</span></span>  
  
- <span data-ttu-id="46d32-191">TOP 子句为空。</span><span class="sxs-lookup"><span data-stu-id="46d32-191">The TOP clause is empty.</span></span> <span data-ttu-id="46d32-192">如果 TOP 子句不为空，则添加 filter 将表示在执行 TOP 之前进行筛选，此操作是不正确的。</span><span class="sxs-lookup"><span data-stu-id="46d32-192">If the TOP clause is not empty, adding the filter would mean filtering before doing TOP, which is not correct.</span></span>  
  
 <span data-ttu-id="46d32-193">上述情况不适用于非关系节点（如 DbConstantExpression 或算术表达式），因为这些节点总是作为现有 SqlSelectStatement 的一部分包含。</span><span class="sxs-lookup"><span data-stu-id="46d32-193">This does not apply to non-relational nodes like DbConstantExpression or arithmetic expressions, because these are always included as part of an existing SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="46d32-194">另外，在遇到联接树（不具有联接父级的联接节点）的根时，将启动新的 SqlSelectStatement。</span><span class="sxs-lookup"><span data-stu-id="46d32-194">Also, when encountering the root of join tree (a join node that does not have a join parent), a new SqlSelectStatement is started.</span></span> <span data-ttu-id="46d32-195">其左侧的所有刺联接子级都聚合到该 SqlSelectStatement 中。</span><span class="sxs-lookup"><span data-stu-id="46d32-195">All of its left spine join children are aggregated into that SqlSelectStatement.</span></span>  
  
 <span data-ttu-id="46d32-196">只要启动新的 SqlSelectStatement 并将当前 SqlSelectStatement 添加到输入中，就可能需要通过添加投影列（SELECT 子句）来完成当前的 SqlSelectStatement（如果不存在 SqlSelectStatement）。</span><span class="sxs-lookup"><span data-stu-id="46d32-196">Whenever a new SqlSelectStatement is started, and the current one is added to the input, the current SqlSelectStatement may need to be completed by adding projection columns (a SELECT clause) if one does not exist.</span></span> <span data-ttu-id="46d32-197">此操作是通过 AddDefaultColumns 方法完成的，该方法查看 SqlSelectStatement 的 FromExtents 并添加由 FromExtents 表示的范围列表引入到投影列的列表范围内的所有列。</span><span class="sxs-lookup"><span data-stu-id="46d32-197">This is done with the method AddDefaultColumns, which looks at the FromExtents of the SqlSelectStatement and adds all the columns that the list of extents represented by FromExtents brings in scope to the list of projected columns.</span></span> <span data-ttu-id="46d32-198">执行此操作的原因是，此时不知道其他节点引用了哪些列。</span><span class="sxs-lookup"><span data-stu-id="46d32-198">This is done, because at that point, it is unknown which columns are referenced by the other nodes.</span></span> <span data-ttu-id="46d32-199">可以对此操作进行优化，以便仅投影稍后可使用的列。</span><span class="sxs-lookup"><span data-stu-id="46d32-199">This can be optimized to only project the columns that can later be used.</span></span>  
  
### <a name="join-flattening"></a><span data-ttu-id="46d32-200">联接平展</span><span class="sxs-lookup"><span data-stu-id="46d32-200">Join Flattening</span></span>  
 <span data-ttu-id="46d32-201">IsParentAJoin 属性有助于确定是否可以平展给定联接。</span><span class="sxs-lookup"><span data-stu-id="46d32-201">The IsParentAJoin property helps determine whether a given join can be flattened.</span></span> <span data-ttu-id="46d32-202">特别是，IsParentAJoin 仅为联接的左侧子级和作为联接的即时输入的每个 DbScanExpression 返回 `true`，在此情况下，该子节点会重用父级稍后将使用的同一 SqlSelectStatement。</span><span class="sxs-lookup"><span data-stu-id="46d32-202">In particular, IsParentAJoin returns `true` only for the left child of a join and for each DbScanExpression that is an immediate input to a join, in which case that child node reuses the same SqlSelectStatement that the parent would later use.</span></span> <span data-ttu-id="46d32-203">有关更多信息，请参见“联接表达式”。</span><span class="sxs-lookup"><span data-stu-id="46d32-203">For more information, see "Join Expressions".</span></span>  
  
### <a name="input-alias-redirecting"></a><span data-ttu-id="46d32-204">输入别名重定向</span><span class="sxs-lookup"><span data-stu-id="46d32-204">Input Alias Redirecting</span></span>  
 <span data-ttu-id="46d32-205">使用符号表完成输入别名重定向。</span><span class="sxs-lookup"><span data-stu-id="46d32-205">Input alias redirecting is accomplished with the symbol table.</span></span>  
  
 <span data-ttu-id="46d32-206">若要解释输入的别名重定向，请参阅中的第一个示例[从命令目录树的最佳实践生成 SQL](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md)。</span><span class="sxs-lookup"><span data-stu-id="46d32-206">To explain input alias redirecting, refer to the first example in [Generating SQL from Command Trees - Best Practices](../../../../../docs/framework/data/adonet/ef/generating-sql-from-command-trees-best-practices.md).</span></span>  <span data-ttu-id="46d32-207">在投影中，需要将“a”重定向为“b”。</span><span class="sxs-lookup"><span data-stu-id="46d32-207">There "a" needed to be redirected to "b" in the projection.</span></span>  
  
 <span data-ttu-id="46d32-208">在创建 SqlSelectStatement 对象时，作为节点的输入的范围将置于 SqlSelectStatement 的 From 属性中。</span><span class="sxs-lookup"><span data-stu-id="46d32-208">When a SqlSelectStatement object is created, the extent that is the input to the node is put in the From property of the SqlSelectStatement.</span></span> <span data-ttu-id="46d32-209">符号 (< symbol_b >) 创建基于输入的绑定名称 ("b") 以表示该范围并将"AS"+ < symbol_b > 追加到 From 子句。</span><span class="sxs-lookup"><span data-stu-id="46d32-209">A Symbol (<symbol_b>) is created based on the input binding name ("b") to represent that extent and "AS  " +  <symbol_b> is appended to the From Clause.</span></span>  <span data-ttu-id="46d32-210">另外，还将此符号添加到 FromExtents 属性。</span><span class="sxs-lookup"><span data-stu-id="46d32-210">The symbol is also added to the FromExtents property.</span></span>  
  
 <span data-ttu-id="46d32-211">此外将符号添加到符号表以将输入的绑定名链接到它 （"b"，< symbol_b >）。</span><span class="sxs-lookup"><span data-stu-id="46d32-211">The symbol is also added to the symbol table to link the input binding name to it ("b", <symbol_b>).</span></span>  
  
 <span data-ttu-id="46d32-212">如果后续节点重用该 SqlSelectStatement，则它将一个项添加到符号表以将其输入绑定名链接到此符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-212">If a subsequent node reuses that SqlSelectStatement, it adds an entry to the symbol table to link its input binding name to that symbol.</span></span> <span data-ttu-id="46d32-213">在本示例中，带输入的绑定名"a"的 DbProjectExpression 将重用 SqlSelectStatement 并添加 ("a"、 \< symbol_b >) 的表。</span><span class="sxs-lookup"><span data-stu-id="46d32-213">In our example, the DbProjectExpression with the input binding name of "a" would reuse the SqlSelectStatement and add ("a", \< symbol_b>) to the table.</span></span>  
  
 <span data-ttu-id="46d32-214">当表达式引用正在重用 SqlSelectStatement 的节点的输入绑定名时，使用符号表将该引用解析为正确的重定向符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-214">When expressions reference the input binding name of the node that is reusing the SqlSelectStatement, that reference is resolved using the symbol table to the correct redirected symbol.</span></span> <span data-ttu-id="46d32-215">"A"从"a.x"解决后若在访问 DbVariableReferenceExpression 表示"a"将解析为符号 < symbol_b >。</span><span class="sxs-lookup"><span data-stu-id="46d32-215">When "a" from "a.x" is resolved while visiting the DbVariableReferenceExpression representing "a" it will resolve to the Symbol <symbol_b>.</span></span>  
  
### <a name="join-alias-flattening"></a><span data-ttu-id="46d32-216">联接别名平展</span><span class="sxs-lookup"><span data-stu-id="46d32-216">Join Alias Flattening</span></span>  
 <span data-ttu-id="46d32-217">联接别名平展是在访问 DbPropertyExpression 时实现的，如标题为 DbPropertyExpression 的一节中所述。</span><span class="sxs-lookup"><span data-stu-id="46d32-217">Join alias flattening is achieved when visiting a DbPropertyExpression as described in the section titled DbPropertyExpression.</span></span>  
  
### <a name="column-name-and-extent-alias-renaming"></a><span data-ttu-id="46d32-218">列名和范围别名重命名</span><span class="sxs-lookup"><span data-stu-id="46d32-218">Column Name and Extent Alias Renaming</span></span>  
 <span data-ttu-id="46d32-219">在标题为 SQL 生成的第二个阶段的部分中所述的生成的第二个阶段中使用别名使用符号仅替换解决列名和范围别名重命名的问题：生成字符串命令。</span><span class="sxs-lookup"><span data-stu-id="46d32-219">The issue of column name and extent alias renaming is addressed by using symbols that only get substituted with aliases in the second phase of the generation described in the section titled Second Phase of SQL Generation: Generating the String Command.</span></span>  
  
## <a name="first-phase-of-the-sql-generation-visiting-the-expression-tree"></a><span data-ttu-id="46d32-220">SQL 生成的第一阶段：访问表达式树</span><span class="sxs-lookup"><span data-stu-id="46d32-220">First Phase of the SQL Generation: Visiting the Expression Tree</span></span>  
 <span data-ttu-id="46d32-221">本节介绍 SQL 生成的第一阶段，在此阶段中将访问表示查询的表达式并生成中间结构（SqlSelectStatement 或 SqlBuilder）。</span><span class="sxs-lookup"><span data-stu-id="46d32-221">This section describes the first phase of SQL generation, when the expression representing the query is visited and an intermediate structure is produced, either a SqlSelectStatement or a SqlBuilder.</span></span>  
  
 <span data-ttu-id="46d32-222">本节描述访问不同的表达式节点类别时遵循的原则以及有关访问特定表达式类型的详细信息。</span><span class="sxs-lookup"><span data-stu-id="46d32-222">This section describes the principles of visiting different expression node categories, and details of visiting specific expression types.</span></span>  
  
### <a name="relational-non-join-nodes"></a><span data-ttu-id="46d32-223">关系（非联接）节点</span><span class="sxs-lookup"><span data-stu-id="46d32-223">Relational (Non-Join) Nodes</span></span>  
 <span data-ttu-id="46d32-224">下面的表达式类型支持非联接节点：</span><span class="sxs-lookup"><span data-stu-id="46d32-224">The following expression types support non-join nodes:</span></span>  
  
- <span data-ttu-id="46d32-225">DbDistinctExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-225">DbDistinctExpression</span></span>  
  
- <span data-ttu-id="46d32-226">DbFilterExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-226">DbFilterExpression</span></span>  
  
- <span data-ttu-id="46d32-227">DbGroupByExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-227">DbGroupByExpression</span></span>  
  
- <span data-ttu-id="46d32-228">DbLimitExpession</span><span class="sxs-lookup"><span data-stu-id="46d32-228">DbLimitExpession</span></span>  
  
- <span data-ttu-id="46d32-229">DbProjectExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-229">DbProjectExpression</span></span>  
  
- <span data-ttu-id="46d32-230">DbSkipExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-230">DbSkipExpression</span></span>  
  
- <span data-ttu-id="46d32-231">DbSortExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-231">DbSortExpression</span></span>  
  
 <span data-ttu-id="46d32-232">访问这些节点时应遵循以下模式：</span><span class="sxs-lookup"><span data-stu-id="46d32-232">Visiting these nodes follows the following pattern:</span></span>  
  
1. <span data-ttu-id="46d32-233">访问关系输入并获取结果 SqlSelectStatement。</span><span class="sxs-lookup"><span data-stu-id="46d32-233">Visit the relational input and get the resulting SqlSelectStatement.</span></span> <span data-ttu-id="46d32-234">对关系节点的输入可以是下列任一项：</span><span class="sxs-lookup"><span data-stu-id="46d32-234">The input to a relational node could be one of the following:</span></span>  
  
    - <span data-ttu-id="46d32-235">关系节点，包括范围（例如 DbScanExpression）。</span><span class="sxs-lookup"><span data-stu-id="46d32-235">A relational node, including an extent (a DbScanExpression, for example).</span></span> <span data-ttu-id="46d32-236">访问此类节点将返回 SqlSelectStatement。</span><span class="sxs-lookup"><span data-stu-id="46d32-236">Visiting such a node returns a SqlSelectStatement.</span></span>  
  
    - <span data-ttu-id="46d32-237">集运算表达式（例如 UNION ALL）。</span><span class="sxs-lookup"><span data-stu-id="46d32-237">A set operation expression (UNION ALL, for example).</span></span> <span data-ttu-id="46d32-238">必须将结果用括号括起，并将其置于新 SqlSelectStatement 的 FROM 子句中。</span><span class="sxs-lookup"><span data-stu-id="46d32-238">The result has to be wrapped in brackets and put in the FROM clause of a new SqlSelectStatement.</span></span>  
  
2. <span data-ttu-id="46d32-239">检查是否可以将当前节点添加到由输入生成的 SqlSelectStatement。</span><span class="sxs-lookup"><span data-stu-id="46d32-239">Check whether the current node can be added to the SqlSelectStatement produced by the input.</span></span> <span data-ttu-id="46d32-240">标题为“将表达式组合为 SQL 语句”这一节对此进行了描述。</span><span class="sxs-lookup"><span data-stu-id="46d32-240">The section titled Grouping Expressions into SQL Statements describes this.</span></span> <span data-ttu-id="46d32-241">如果不可以添加，则</span><span class="sxs-lookup"><span data-stu-id="46d32-241">If not,</span></span>  
  
    - <span data-ttu-id="46d32-242">弹出当前的 SqlSelectStatement 对象。</span><span class="sxs-lookup"><span data-stu-id="46d32-242">Pop the current SqlSelectStatement object.</span></span>  
  
    - <span data-ttu-id="46d32-243">创建新的 SqlSelectStatement 对象并将弹出的 SqlSelectStatement 添加为新 SqlSelectStatement 对象的 From 属性。</span><span class="sxs-lookup"><span data-stu-id="46d32-243">Create a new SqlSelectStatement object and add the popped SqlSelectStatement as the FROM of the new SqlSelectStatement object.</span></span>  
  
    - <span data-ttu-id="46d32-244">将新对象置于堆栈的顶部。</span><span class="sxs-lookup"><span data-stu-id="46d32-244">Put the new object on top of the stack.</span></span>  
  
3. <span data-ttu-id="46d32-245">将输入表达式绑定从输入中重定向到正确的符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-245">Redirect the input expression binding to the correct symbol from the input.</span></span> <span data-ttu-id="46d32-246">此信息保留在 SqlSelectStatement 对象中。</span><span class="sxs-lookup"><span data-stu-id="46d32-246">This information is maintained in the SqlSelectStatement object.</span></span>  
  
4. <span data-ttu-id="46d32-247">添加新的 SymbolTable 范围。</span><span class="sxs-lookup"><span data-stu-id="46d32-247">Add a new SymbolTable scope.</span></span>  
  
5. <span data-ttu-id="46d32-248">访问表达式的非输入部分（例如投影和谓词）。</span><span class="sxs-lookup"><span data-stu-id="46d32-248">Visit the non-input part of the expression (for example, Projection and Predicate).</span></span>  
  
6. <span data-ttu-id="46d32-249">弹出已添加到全局堆栈的所有对象。</span><span class="sxs-lookup"><span data-stu-id="46d32-249">Pop all the objects added to the global stacks.</span></span>  
  
 <span data-ttu-id="46d32-250">DbSkipExpression 在 SQL 中没有直接等效项。</span><span class="sxs-lookup"><span data-stu-id="46d32-250">DbSkipExpression not have a direct equivalent in SQL.</span></span> <span data-ttu-id="46d32-251">从逻辑上说，它将转换为：</span><span class="sxs-lookup"><span data-stu-id="46d32-251">Logically, it is translated into:</span></span>  
  
```  
SELECT Y.x1, Y.x2, ..., Y.xn  
FROM (  
   SELECT X.x1, X.x2, ..., X.xn, row_number() OVER (ORDER BY sk1, sk2, ...) AS [row_number]   
   FROM input as X   
   ) as Y  
WHERE Y.[row_number] > count   
ORDER BY sk1, sk2, ...  
```  
  
### <a name="join-expressions"></a><span data-ttu-id="46d32-252">联接表达式</span><span class="sxs-lookup"><span data-stu-id="46d32-252">Join Expressions</span></span>  
 <span data-ttu-id="46d32-253">以下表达式将视为联接表达式，并且 VisitJoinExpression 方法将按某种常见方式处理它们：</span><span class="sxs-lookup"><span data-stu-id="46d32-253">The following are considered join expressions and they are processed in a common way, by the VisitJoinExpression method:</span></span>  
  
- <span data-ttu-id="46d32-254">DbApplyExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-254">DbApplyExpression</span></span>  
  
- <span data-ttu-id="46d32-255">DbJoinExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-255">DbJoinExpression</span></span>  
  
- <span data-ttu-id="46d32-256">DbCrossJoinExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-256">DbCrossJoinExpression</span></span>  
  
 <span data-ttu-id="46d32-257">以下是访问步骤：</span><span class="sxs-lookup"><span data-stu-id="46d32-257">The following are the visit steps:</span></span>  
  
 <span data-ttu-id="46d32-258">第一步，在访问子级之前，调用 IsParentAJoin 以检查联接节点是否为左刺方向的联接的子级。</span><span class="sxs-lookup"><span data-stu-id="46d32-258">First, before visiting the children, IsParentAJoin is invoked to check whether the join node is a child of a join along a left spine.</span></span> <span data-ttu-id="46d32-259">如果它返回 false，则启动新的 SqlSelectStatement。</span><span class="sxs-lookup"><span data-stu-id="46d32-259">If it returns false, a new SqlSelectStatement is started.</span></span> <span data-ttu-id="46d32-260">从这种意义上来说，由于父级（联接节点）将为可能要使用的子级创建 SqlSelectStatement，因此将按照不同的方式从剩余节点访问联接。</span><span class="sxs-lookup"><span data-stu-id="46d32-260">In that sense, joins are visited differently from the rest of the nodes, as the parent (the join node) creates the SqlSelectStatement for the children to possibly use.</span></span>  
  
 <span data-ttu-id="46d32-261">第二步，一次处理一个输入。</span><span class="sxs-lookup"><span data-stu-id="46d32-261">Second, process the inputs one at a time.</span></span> <span data-ttu-id="46d32-262">对于每个输入：</span><span class="sxs-lookup"><span data-stu-id="46d32-262">For each input:</span></span>  
  
1. <span data-ttu-id="46d32-263">访问输入。</span><span class="sxs-lookup"><span data-stu-id="46d32-263">Visit the input.</span></span>  
  
2. <span data-ttu-id="46d32-264">通过调用 ProcessJoinInputResult对访问输入的结果进行后续处理，此操作负责在访问联接表达式的子级后保留符号表并完成子级生成的 SqlSelectStatement。</span><span class="sxs-lookup"><span data-stu-id="46d32-264">Post process the result of visiting the input by invoking ProcessJoinInputResult, which is responsible for maintaining the symbol table after visiting a child of a join expression and possibly finishing the SqlSelectStatement produced by the child.</span></span> <span data-ttu-id="46d32-265">子级的结果可以是下列项之一：</span><span class="sxs-lookup"><span data-stu-id="46d32-265">The child's result could be one of the following:</span></span>  
  
    - <span data-ttu-id="46d32-266">将向其添加父级的 SqlSelectStatement 之外的 SqlSelectStatement。</span><span class="sxs-lookup"><span data-stu-id="46d32-266">A SqlSelectStatement different from the one to which the parent will be added.</span></span> <span data-ttu-id="46d32-267">在此情况下，可能需要通过添加默认列来完成它。</span><span class="sxs-lookup"><span data-stu-id="46d32-267">In such case, it may need to be completed by adding default columns.</span></span> <span data-ttu-id="46d32-268">如果输入是一个联接，则需要创建新的联接符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-268">If the input was a Join, you need to create a new join symbol.</span></span> <span data-ttu-id="46d32-269">否则，将创建普通符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-269">Otherwise, create a normal symbol.</span></span>  
  
    - <span data-ttu-id="46d32-270">一个范围（例如 DbScanExpression），在此情况下，只是将其添加到父级的 SqlSelectStatement 的输入列表。</span><span class="sxs-lookup"><span data-stu-id="46d32-270">An extent (a DbScanExpression, for example), in which case it is simply added to the list of inputs of the parent’s SqlSelectStatement.</span></span>  
  
    - <span data-ttu-id="46d32-271">非 SqlSelectStatement，在此情况下，使用括号将其括起。</span><span class="sxs-lookup"><span data-stu-id="46d32-271">Not a SqlSelectStatement, in which case it is wrapped with brackets.</span></span>  
  
    - <span data-ttu-id="46d32-272">向其添加父级的同一 SqlSelectStatement。</span><span class="sxs-lookup"><span data-stu-id="46d32-272">The same SqlSelectStatement to which the parent is added.</span></span> <span data-ttu-id="46d32-273">在此情况下，需要将 FromExtents 列表中的符号替换为表示所有这些项的单个新 JoinSymbol。</span><span class="sxs-lookup"><span data-stu-id="46d32-273">In such case, the symbols in the FromExtents list need to be replaced with a single new JoinSymbol representing them all.</span></span>  
  
    - <span data-ttu-id="46d32-274">对于前三种情况，调用 AddFromSymbol 以添加 AS 子句并更新符号表。</span><span class="sxs-lookup"><span data-stu-id="46d32-274">For the first three cases, AddFromSymbol is called to add the AS clause, and update the symbol table.</span></span>  
  
 <span data-ttu-id="46d32-275">第三步，访问联接条件（如果有）。</span><span class="sxs-lookup"><span data-stu-id="46d32-275">Third, the join condition (if any) is visited.</span></span>  
  
### <a name="set-operations"></a><span data-ttu-id="46d32-276">Set 运算</span><span class="sxs-lookup"><span data-stu-id="46d32-276">Set Operations</span></span>  
 <span data-ttu-id="46d32-277">集运算 DbUnionAllExpression、DbExceptExpression 和 DbIntersectExpression 都由方法 VisitSetOpExpression 处理。</span><span class="sxs-lookup"><span data-stu-id="46d32-277">The set operations DbUnionAllExpression, DbExceptExpression, and DbIntersectExpression are processed by the method VisitSetOpExpression.</span></span> <span data-ttu-id="46d32-278">它创建形状的 SqlBuilder</span><span class="sxs-lookup"><span data-stu-id="46d32-278">It creates a SqlBuilder of the shape</span></span>  
  
```xml  
<leftSqlSelectStatement> <setOp> <rightSqlSelectStatement>  
```  
  
 <span data-ttu-id="46d32-279">其中\<leftSqlSelectStatement > 和\<rightSqlSelectStatement > 是通过访问每个输入，获得的 Sqlselectstatement 和\<setOp > 是对应的运算 (例如 UNION ALL)。</span><span class="sxs-lookup"><span data-stu-id="46d32-279">Where \<leftSqlSelectStatement> and \<rightSqlSelectStatement> are SqlSelectStatements obtained by visiting each of the inputs, and \<setOp> is the corresponding operation (UNION ALL for example).</span></span>  
  
### <a name="dbscanexpression"></a><span data-ttu-id="46d32-280">DbScanExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-280">DbScanExpression</span></span>  
 <span data-ttu-id="46d32-281">如果在联接上下文中访问 DbScanExpression（作为一个联接的输入，该联接是另一个联接的左侧子级），则它会返回一个 SqlBuilder，后者带有相应目标（为定义查询、表或视图）的目标 SQL。</span><span class="sxs-lookup"><span data-stu-id="46d32-281">If visited in a join context (as an input to a join that is a left child of another join), DbScanExpression returns a SqlBuilder with the target SQL for the corresponding target, which is either a defining query, table, or a view.</span></span> <span data-ttu-id="46d32-282">否则，创建一个新的 SqlSelectStatement，其 FROM 字段设置为与相应目标对应。</span><span class="sxs-lookup"><span data-stu-id="46d32-282">Otherwise, a new SqlSelectStatement is created with the FROM field set to correspond to the corresponding target.</span></span>  
  
### <a name="dbvariablereferenceexpression"></a><span data-ttu-id="46d32-283">DbVariableReferenceExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-283">DbVariableReferenceExpression</span></span>  
 <span data-ttu-id="46d32-284">访问 DbVariableReferenceExpression 将基于符号表中的某个查找返回与变量引用表达式对应的符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-284">The visit of a DbVariableReferenceExpression returns the Symbol corresponding to that variable reference expression based on a look up in the symbol table.</span></span>  
  
### <a name="dbpropertyexpression"></a><span data-ttu-id="46d32-285">DbPropertyExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-285">DbPropertyExpression</span></span>  
 <span data-ttu-id="46d32-286">联接别名平展是在访问 DbPropertyExpression 时标识并处理的。</span><span class="sxs-lookup"><span data-stu-id="46d32-286">Join alias flattening is identified and processed when visiting a DbPropertyExpression.</span></span>  
  
 <span data-ttu-id="46d32-287">首先访问 Instance 属性，并且结果为 Symbol、JoinSymbol 或 SymbolPair。</span><span class="sxs-lookup"><span data-stu-id="46d32-287">The Instance property is first visited and the result is a Symbol, a JoinSymbol, or a SymbolPair.</span></span> <span data-ttu-id="46d32-288">以下是对这三种情况的处理方式：</span><span class="sxs-lookup"><span data-stu-id="46d32-288">Here is how these three cases are handled:</span></span>  
  
- <span data-ttu-id="46d32-289">如果返回 JoinSymbol，则其 NameToExtent 属性包含所需属性的符号。</span><span class="sxs-lookup"><span data-stu-id="46d32-289">If a JoinSymbol is returned, than its NameToExtent property contains a symbol for the needed property.</span></span> <span data-ttu-id="46d32-290">如果联接符号表示嵌套联接，则返回带联接符号的新 Symbol 对，以跟踪将用作实例别名的符号和表示实际属性的符号，从而进行进一步的解析。</span><span class="sxs-lookup"><span data-stu-id="46d32-290">If the join symbol represents a nested join, a new Symbol pair is returned with the join symbol to track the symbol that would be used as the instance alias, and the symbol representing the actual property for further resolving.</span></span>  
  
- <span data-ttu-id="46d32-291">如果返回 SymbolPair 且 Column 部分为联接符号，则再次返回联接符号，而此时列属性将更新为指向当前属性表达式所表示的属性。</span><span class="sxs-lookup"><span data-stu-id="46d32-291">If a SymbolPair is returned and the Column part is a join symbol, a join symbol is again returned, but now the column property is updated to point to the property represented by the current property expression.</span></span> <span data-ttu-id="46d32-292">否则，返回一个 SqlBuilder，它使用 SymbolPair 源作为别名并使用当前属性的符号作为列。</span><span class="sxs-lookup"><span data-stu-id="46d32-292">Otherwise a SqlBuilder is returned with the SymbolPair source as the alias, and the symbol for the current property as the column.</span></span>  
  
- <span data-ttu-id="46d32-293">如果返回 Symbol，则 Visit 方法返回一个 SqlBuilder 方法，它使用该实例作为别名并使用属性名作为列名。</span><span class="sxs-lookup"><span data-stu-id="46d32-293">If a Symbol is returned, the Visit method returns a SqlBuilder method with that instance as the alias, and the property name as column name.</span></span>  
  
### <a name="dbnewinstanceexpression"></a><span data-ttu-id="46d32-294">DbNewInstanceExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-294">DbNewInstanceExpression</span></span>  
 <span data-ttu-id="46d32-295">在用作 DbProjectExpression 的 Projection 属性时，DbNewInstanceExpression 会生成参数的以逗号分隔的列表以表示投影列。</span><span class="sxs-lookup"><span data-stu-id="46d32-295">When used as the Projection property of DbProjectExpression, DbNewInstanceExpression produces a comma-separated list of the arguments to represent the projected columns.</span></span>  
  
 <span data-ttu-id="46d32-296">若 DbNewInstanceExpression 具有集合返回类型并定义一个作为自变量提供的表达式的新集合，则将单独处理以下三种情况：</span><span class="sxs-lookup"><span data-stu-id="46d32-296">When DbNewInstanceExpression has a collection return type, and defines a new collection of the expressions provided as arguments, the following three cases are handled separately:</span></span>  
  
- <span data-ttu-id="46d32-297">如果 DbNewInstanceExpression 将 DbElementExpression 用作唯一自变量，则将对其进行转换，如下所示：</span><span class="sxs-lookup"><span data-stu-id="46d32-297">If DbNewInstanceExpression has DbElementExpression as the only argument, it is translated as follows:</span></span>  
  
    ```  
    NewInstance(Element(X)) =>  SELECT TOP 1 …FROM X  
    ```  
  
 <span data-ttu-id="46d32-298">如果 DbNewInstanceExpression 不具有任何参数（表示空表），则将 DbNewInstanceExpression 转换为：</span><span class="sxs-lookup"><span data-stu-id="46d32-298">If DbNewInstanceExpression has no arguments (represents an empty table), DbNewInstanceExpression is translated into:</span></span>  
  
```  
SELECT CAST(NULL AS <primitiveType>) as X  
FROM (SELECT 1) AS Y WHERE 1=0  
```  
  
 <span data-ttu-id="46d32-299">否则，DbNewInstanceExpression 会生成自变量的 UNION ALL 通道：</span><span class="sxs-lookup"><span data-stu-id="46d32-299">Otherwise DbNewInstanceExpression builds a union-all ladder of the arguments:</span></span>  
  
```  
SELECT <visit-result-arg1> as X  
UNION ALL SELECT <visit-result-arg2> as X  
UNION ALL …  
UNION ALL SELECT <visit-result-argN> as X  
```  
  
### <a name="dbfunctionexpression"></a><span data-ttu-id="46d32-300">DbFunctionExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-300">DbFunctionExpression</span></span>  
 <span data-ttu-id="46d32-301">规范函数和内置函数的处理方式相同：如果它们需要特别处理（例如，从 TRIM(string) 转换为 LTRIM(RTRIM(string)），则将调用适当的处理程序。</span><span class="sxs-lookup"><span data-stu-id="46d32-301">Canonical and built-in functions are processed the same way: if they need special handling (TRIM(string) to  LTRIM(RTRIM(string), for example), the appropriate handler is invoked.</span></span> <span data-ttu-id="46d32-302">否则，将它们转换为 FunctionName(arg1, arg2, ..., argn)。</span><span class="sxs-lookup"><span data-stu-id="46d32-302">Otherwise they are translated to FunctionName(arg1, arg2, ..., argn).</span></span>  
  
 <span data-ttu-id="46d32-303">字典用于跟踪哪些函数需要特别处理及其相应的处理程序。</span><span class="sxs-lookup"><span data-stu-id="46d32-303">Dictionaries are used to keep track of which functions need special handling and their appropriate handlers.</span></span>  
  
 <span data-ttu-id="46d32-304">用户定义的函数将转换为 NamespaceName.FunctionName(arg1, arg2, ..., argn)。</span><span class="sxs-lookup"><span data-stu-id="46d32-304">User-defined functions are tanslated to NamespaceName.FunctionName(arg1, arg2, ..., argn).</span></span>  
  
### <a name="dbelementexpression"></a><span data-ttu-id="46d32-305">DbElementExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-305">DbElementExpression</span></span>  
 <span data-ttu-id="46d32-306">仅在访问用于表示标量子查询的 DbElementExpression 时调用访问 DbElementExpression 的方法。</span><span class="sxs-lookup"><span data-stu-id="46d32-306">The method that visits DbElementExpression is only invoked for visiting a DbElementExpression when used to represent a scalar subquery.</span></span> <span data-ttu-id="46d32-307">因此，DbElementExpression 将转换为完整的 SqlSelectStatement，并用括号将其括起。</span><span class="sxs-lookup"><span data-stu-id="46d32-307">Therefore, DbElementExpression translates into a complete SqlSelectStatement and adds brackets around it.</span></span>  
  
### <a name="dbquantifierexpression"></a><span data-ttu-id="46d32-308">DbQuantifierExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-308">DbQuantifierExpression</span></span>  
 <span data-ttu-id="46d32-309">根据表达式类型（Any 或 All），将 DbQuantifierExpression 转换为：</span><span class="sxs-lookup"><span data-stu-id="46d32-309">Depending on the expression type (Any or All), DbQuantifierExpression is translated it as:</span></span>  
  
```  
Any(input, x) => Exists(Filter(input,x))  
All(input, x) => Not Exists(Filter(input, not(x))  
```  
  
### <a name="dbnotexpression"></a><span data-ttu-id="46d32-310">DbNotExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-310">DbNotExpression</span></span>  
 <span data-ttu-id="46d32-311">在某些情况下，可以使用其输入表达式折叠 DbNotExpression 的转换。</span><span class="sxs-lookup"><span data-stu-id="46d32-311">In some cases it is possible to collapse the translation of DbNotExpression with its input expression.</span></span> <span data-ttu-id="46d32-312">例如：</span><span class="sxs-lookup"><span data-stu-id="46d32-312">For example:</span></span>  
  
```  
Not(IsNull(a)) =>  "a IS NOT NULL"  
Not(All(input, x) => Not (Not Exists(Filter(input, not(x))) => Exists(Filter(input, not(x))  
```  
  
 <span data-ttu-id="46d32-313">执行第二次折叠的原因是，在转换类型为 All 的 DbQuantifierExpression 时提供程序导致效率较低。</span><span class="sxs-lookup"><span data-stu-id="46d32-313">The reason the second collapse is performed is because inefficiencies were introduced by the provider when translating DbQuantifierExpression of type All.</span></span> <span data-ttu-id="46d32-314">因此，实体框架无法执行简化。</span><span class="sxs-lookup"><span data-stu-id="46d32-314">Thus the Entity Framework could not have done the simplification.</span></span>  
  
### <a name="dbisemptyexpression"></a><span data-ttu-id="46d32-315">DbIsEmptyExpression</span><span class="sxs-lookup"><span data-stu-id="46d32-315">DbIsEmptyExpression</span></span>  
 <span data-ttu-id="46d32-316">将 DbIsEmptyExpression 转换为：</span><span class="sxs-lookup"><span data-stu-id="46d32-316">DbIsEmptyExpression is translated as:</span></span>  
  
```  
IsEmpty(inut) = Not Exists(input)  
```  
  
## <a name="second-phase-of-sql-generation-generating-the-string-command"></a><span data-ttu-id="46d32-317">SQL 生成的第二个阶段：生成字符串命令</span><span class="sxs-lookup"><span data-stu-id="46d32-317">Second Phase of SQL Generation: Generating the String Command</span></span>  
 <span data-ttu-id="46d32-318">在生成字符串 SQL 命令时，SqlSelectStatement 会生成符号的实际别名，这将解决列名和范围别名的重命名问题。</span><span class="sxs-lookup"><span data-stu-id="46d32-318">When generating a string SQL command, the SqlSelectStatement produces actual aliases for the symbols, which addresses the issue of column name and extent alias renaming.</span></span>  
  
 <span data-ttu-id="46d32-319">在将 SqlSelectStatement 对象写入字符串时会发生范围别名重命名。</span><span class="sxs-lookup"><span data-stu-id="46d32-319">Extent alias renaming occurs while writing the SqlSelectStatement object into a string.</span></span> <span data-ttu-id="46d32-320">首先，创建外部范围使用的所有别名的列表。</span><span class="sxs-lookup"><span data-stu-id="46d32-320">First create a list of all the aliases used by the outer extents.</span></span> <span data-ttu-id="46d32-321">对于 FromExtents（如果它不为 null，则为 AllJoinExtents）中的每个符号，如果该符号与任何外部范围发生冲突，则对该符号进行重命名。</span><span class="sxs-lookup"><span data-stu-id="46d32-321">Each symbol in the FromExtents (or AllJoinExtents if it is non-null), gets renamed if it collides with any of the outer extents.</span></span> <span data-ttu-id="46d32-322">如果需要进行重命名，则它不会与 AllExtentNames 中收集的任何范围发生冲突。</span><span class="sxs-lookup"><span data-stu-id="46d32-322">If renaming is needed, it will not conflict with any of the extents collected in AllExtentNames.</span></span>  
  
 <span data-ttu-id="46d32-323">在将 Symbol 对象写入字符串时会发生列重命名。</span><span class="sxs-lookup"><span data-stu-id="46d32-323">Column renaming occurs while writing a Symbol object to a string.</span></span> <span data-ttu-id="46d32-324">第一阶段中的 AddDefaultColumns 已确定是否必须对某个列符号进行重命名。</span><span class="sxs-lookup"><span data-stu-id="46d32-324">AddDefaultColumns in the first phase has determined if a certain column symbol has to be renamed.</span></span> <span data-ttu-id="46d32-325">在第二阶段中，只有进行重命名才能确保生成的名称不会与 AllColumnNames 中使用的任何名称发生冲突。</span><span class="sxs-lookup"><span data-stu-id="46d32-325">In the second phase only the rename occurs making sure that the name produced does not conflict with any name used in AllColumnNames</span></span>  
  
 <span data-ttu-id="46d32-326">若要生成同时为范围别名和列的唯一名称，请使用 < existing_name > _n，其中 n 是尚未使用的最小别名。</span><span class="sxs-lookup"><span data-stu-id="46d32-326">To produce unique names both for extent aliases and for columns, use <existing_name>_n where n is the smallest alias that has not been used yet.</span></span> <span data-ttu-id="46d32-327">所有别名的全局列表加大了对层叠重命名的需要。</span><span class="sxs-lookup"><span data-stu-id="46d32-327">The global list of all aliases increases the need for cascading renames.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46d32-328">请参阅</span><span class="sxs-lookup"><span data-stu-id="46d32-328">See also</span></span>

- [<span data-ttu-id="46d32-329">示例提供程序中的 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="46d32-329">SQL Generation in the Sample Provider</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation-in-the-sample-provider.md)
