---
title: "-INCREMENTAL (Link Incrementally)"
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
H1: /INCREMENTAL (Link Incrementally)
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
caps.latest.revision: 12
manager: ghogen
translation.priority.ht: 
  - de-de
  - es-es
  - fr-fr
  - it-it
  - ja-jp
  - ko-kr
  - ru-ru
  - zh-cn
  - zh-tw
translation.priority.mt: 
  - cs-cz
  - pl-pl
  - pt-br
  - tr-tr
---
# -INCREMENTAL (Link Incrementally)
```  
/INCREMENTAL[:NO]  
```  
  
## Remarks  
 Controls how the linker handles incremental linking.  
  
 By default, the linker runs in incremental mode. To override a default incremental link, specify /INCREMENTAL:NO.  
  
 An incrementally linked program is functionally equivalent to a program that is non-incrementally linked. However, because it is prepared for subsequent incremental links, an incrementally linked executable, static library, or dynamic-link library file:  
  
-   Is larger than a non-incrementally linked program because of padding of code and data. Padding enables the linker to increase the size of functions and data without recreating the file.  
  
-   May contain jump thunks to handle relocation of functions to new addresses.  
  
    > [!NOTE]
    >  To ensure that your final release build does not contain padding or thunks, link your program non-incrementally.  
  
 To link incrementally regardless of the default, specify /INCREMENTAL. When this option is selected, the linker issues a warning if it cannot link incrementally, and then links the program non-incrementally. Certain options and situations override /INCREMENTAL.  
  
 Most programs can be linked incrementally. However, some changes are too great, and some options are incompatible with incremental linking. LINK performs a full link if any of the following options are specified:  
  
-   Link Incrementally is not selected (/INCREMENTAL:NO)  
  
-   /OPT:REF is selected  
  
-   /OPT:ICF is selected  
  
-   /OPT:LBR is selected  
  
-   /ORDER is selected  
  
 /INCREMENTAL is implied when [/DEBUG](../VS_visualcpp/-DEBUG--Generate-Debug-Info-.md) is specified.  
  
 Additionally, LINK performs a full link if any of the following situations occur:  
  
-   The incremental status (.ilk) file is missing. (LINK creates a new .ilk file in preparation for subsequent incremental linking.)  
  
-   There is no write permission for the .ilk file. (LINK ignores the .ilk file and links non-incrementally.)  
  
-   The .exe or .dll output file is missing.  
  
-   The timestamp of the .ilk, .exe, or .dll is changed.  
  
-   A LINK option is changed. Most LINK options, when changed between builds, cause a full link.  
  
-   An object (.obj) file is added or omitted.  
  
### To set this linker option in the Visual Studio development environment  
  
1.  Open the project's **Property Pages** dialog box. For details, see [Working with Project Properties](../VS_visualcpp/Working-with-Project-Properties.md).  
  
2.  Select the **Linker** folder.  
  
3.  Select the **General** property page.  
  
4.  Modify the **Enable Incremental Linking** property.  
  
### To set this linker option programmatically  
  
1.  See <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental?qualifyHint=False>.  
  
## See Also  
 [Setting Linker Options](../VS_visualcpp/Setting-Linker-Options.md)   
 [Linker Options](../VS_visualcpp/Linker-Options.md)