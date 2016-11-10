---
title: "-FC (Full Path of Source Code File in Diagnostics)"
ms.custom: na
ms.date: 10/03/2016
ms.devlang: 
  - C++
ms.prod: visual-studio-dev14
ms.reviewer: na
ms.suite: na
ms.technology: 
  - devlang-cpp
ms.tgt_pltfrm: na
ms.topic: article
H1: /FC (Full Path of Source Code File in Diagnostics)
ms.assetid: 1f11414e-cb42-421b-be68-9d369aab036b
caps.latest.revision: 14
manager: ghogen
translation.priority.ht: 
  - cs-cz
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - pl-pl
  - pt-br
  - ru-ru
  - tr-tr
  - zh-cn
  - zh-tw
---
# -FC (Full Path of Source Code File in Diagnostics)
Causes the compiler to display the full path of source code files passed to the compiler in diagnostics.  
  
## Syntax  
  
```  
/FC  
```  
  
## Remarks  
 Consider the following code sample:  
  
```  
// compiler_option_FC.cpp  
int main( ) {  
   int i   // C2143  
}  
```  
  
 Without **/FC**, the diagnostic text would look similar to this diagnostic text:  
  
-   compiler_option_FC.cpp(5) : error C2143: syntax error : missing ';' before '}'  
  
 With **/FC**, the diagnostic text would look similar to this diagnostic text:  
  
-   c:\test\compiler_option_FC.cpp(5) : error C2143: syntax error : missing ';' before '}'  
  
 **/FC** is also needed if you want to see the full path of a file name when using the __FILE\_\_ macro.  See [Predefined Macros](../VS_visualcpp/Predefined-Macros.md) for more information on \__FILE\_\_.  
  
 The **/FC** option is implied by **/ZI**. For more information about **/ZI**, see [/Z7, /Zi, /ZI (Debug Information Format)](../VS_visualcpp/-Z7---Zi---ZI--Debug-Information-Format-.md).  
  
### To set this compiler option in the Visual Studio development environment  
  
1.  Open the project's **Property Pages** dialog box. For details, see [How to: Open Project Property Pages](../Topic/How%20to:%20Open%20Project%20Property%20Pages.md).  
  
2.  Expand the **Configuration Properties** node.  
  
3.  Expand the **C/C++** node.  
  
4.  Select the **Advanced** property page.  
  
5.  Modify the **Use Full Paths** property.  
  
### To set this linker option programmatically  
  
1.  See <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.UseFullPaths?qualifyHint=False>.  
  
## See Also  
 [Compiler Options](../VS_visualcpp/Compiler-Options.md)   
 [Setting Compiler Options](../VS_visualcpp/Setting-Compiler-Options.md)