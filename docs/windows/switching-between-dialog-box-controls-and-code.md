---
title: "Switching Between Dialog Box Controls and Code"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "events [C++], viewing for controls"
  - "Windows messages [C++], controls"
  - "messages [C++], viewing for dialog boxes"
  - "Dialog editor, accessing code"
  - "code [C++], switching from Dialog Editor"
  - "controls [C++], jumping to code"
  - "Dialog editor, switching between controls and code"
ms.assetid: 7da73815-b853-4203-ba45-bbe570695122
caps.latest.revision: 7
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# Switching Between Dialog Box Controls and Code
In MFC applications, you can double-click on dialog box controls to jump to their handler code or to quickly create stub handler functions.  
  
 With a control selected, click the **ControlEvents** button or the **Messages** button in the [Properties window](../Topic/Properties%20Window.md) to view a complete list of Windows messages and events available for the selected item. Choose from the list to create or edit handler functions.  
  
### To jump to code from the dialog editor  
  
1.  Double-click on a control within the dialog box to jump to the declaration for its most-recently implemented message handling function. (For ATL-based dialog classes, you always jump to the constructor definition.)  
  
### To view events for a control  
  
1.  With a control selected, click the **ControlEvents** button in the [Properties window](../Topic/Properties%20Window.md).  
  
    > [!NOTE]
    >  Clicking the **ControlEvents** button when the *dialog box* has focus exposes a list of all the controls in the dialog box, which you can then expand to edit the events for the individual controls.  
  
     When a single control has focus in the dialog box, you can right-click it and select **Add Event Handler** from the shortcut menu. This enables you to specify the class to which the handler is added. For more information, see [Adding an Event Handler](../ide/adding-an-event-handler--visual-c---.md).  
  
### To view messages for a dialog box  
  
1.  With the dialog box selected, click the **Messages** button in the [Properties window](../Topic/Properties%20Window.md).  
  
 For information on adding resources to managed projects, please see [Resources in Applications](../Topic/Resources%20in%20Desktop%20Apps.md) in the *.NET Framework Developer's Guide.* For information on manually adding resource files to managed projects, accessing resources, displaying static resources, and assigning resources strings to properties, see [Walkthrough: Localizing Windows Forms](assetId:///9a96220d-a19b-4de0-9f48-01e5d82679e5) and [Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md).  
  
 Requirements  
  
 Win32  
  
## See Also  
 [Dialog Editor](../mfc/dialog-editor.md)