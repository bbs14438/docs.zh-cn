---
title: -定义 (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- -d compiler option [Visual Basic]
- /d compiler option [Visual Basic]
- -define compiler option [Visual Basic]
- d compiler option [Visual Basic]
- /define compiler option [Visual Basic]
- define compiler option [Visual Basic]
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4de37c58543aed9ed13be8b0d2bcec9830ca9082
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="-define-visual-basic"></a>-定义 (Visual Basic)
定义条件编译器常数。  
  
## <a name="syntax"></a>语法  
  
```  
-define:["]symbol[=value][,symbol[=value]]["]  
' -or-  
-d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## <a name="arguments"></a>自变量  
  
|术语|定义|  
|---|---|  
|`symbol`|必需。 要定义的符号。|  
|`value`|可选。 指派给 `symbol` 的值。 如果`value`是一个字符串，则必须由反斜杠/双引号序列括起来 (\\") 而不是引号引起来。 如果未指定值，则视为 True。|  
  
## <a name="remarks"></a>备注  
 `-define`选项才起作用类似于使用`#Const`在源代码文件中，除使用定义的常数的预处理器指令`-define`是公共的并将应用到项目中的所有文件。  
  
 可以将由此选项创建的符号同 `#If`...`Then`...`#Else` 指令一起使用，以对源文件进行条件编译。  
  
 `-d` 是 `-define` 的缩写形式。  
  
 通过使用逗号分隔符号定义，可以用 `-define` 定义多个符号。  
  
|在 Visual Studio 集成开发环境中设置/定义|  
|---|  
|1.在 **“解决方案资源管理器”**中选择一个项目。 在“项目”菜单上，单击“属性”。 <br />2.单击“编译”选项卡。<br />3.单击 **“高级”**。<br />4.修改中的值**自定义常量**框。|  
  
## <a name="example"></a>示例  
 下面的代码定义并使用两个条件编译器常数。  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [Visual Basic 命令行编译器](../../../visual-basic/reference/command-line-compiler/index.md)  
 [#If...Then...#Else 指令](../../../visual-basic/language-reference/directives/if-then-else-directives.md)  
 [#Const 指令](../../../visual-basic/language-reference/directives/const-directive.md)  
 [示例编译命令行](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
