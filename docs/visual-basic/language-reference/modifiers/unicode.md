---
title: Unicode (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Unicode
helpviewer_keywords:
- Unicode, external references
- Declare statement [Visual Basic], marshaling strings
- Unicode keyword [Visual Basic]
- Unicode, marshaling strings
ms.assetid: 0021d5ff-3209-444e-8497-420f3e6ee075
ms.openlocfilehash: a61fd8e10c39569d92dd84180f678a1ff05a9310
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="unicode-visual-basic"></a>Unicode (Visual Basic)
指定 Visual Basic 应封送所有字符串转换为 Unicode 值，无论所声明的外部过程的名称。  
  
 在调用在项目外部定义的过程时，Visual Basic 编译器没有访问它必须具备正确调用过程的信息。 此信息包括过程所在的位置、 标识的方式、 其调用的序列和返回类型和字符串字符将其设置使用。 [声明语句](../../../visual-basic/language-reference/statements/declare-statement.md)创建对外部过程的引用，并提供这些必需的信息。  
  
 `charsetmodifier`部分`Declare`语句提供期间对外部过程的调用封送字符串的字符组信息。 它还会影响 Visual Basic 会外部过程名称的外部文件的搜索。 `Unicode`修饰符指定 Visual Basic 应封送的所有字符串转换为 Unicode 值和应查找而无需在搜索过程中修改其名称的过程。  
  
 如果不指定任何字符集修饰符，则`Ansi`是默认设置。  
  
## <a name="remarks"></a>备注  
 `Unicode`修饰符可用于在此上下文中：  
  
 [Declare 语句](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
## <a name="smart-device-developer-notes"></a>智能设备的开发人员说明  
 此关键字不受支持。  
  
## <a name="see-also"></a>请参阅  
 [Ansi](../../../visual-basic/language-reference/modifiers/ansi.md)  
 [Auto](../../../visual-basic/language-reference/modifiers/auto.md)  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)
