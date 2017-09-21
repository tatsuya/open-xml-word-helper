[![Build status](https://ci.appveyor.com/api/projects/status/q3f9vpm36k75501c?svg=true)](https://ci.appveyor.com/project/tatsuya/open-xml-word-helper)

###### Note
* Ignore all properties and non-generic meethods because you are always interested in a specific type. (There is no generic property.)
* Use only AppendChild(...) rather than mix PrependChild(...) and AppendChild(...)
* ParagraphProperties must come before Paragraph to take effect.
* RunProperties must come before Run to take effect.

###### Getter methods of OpenXmlElement
|Method|Meaning|
|---|---|
|Descendants<T>()|Get children, grandchildren and so on|
|Elements<T>()|Get immediate children|
|GetFirstChild<T>()|Get the first child|
  
###### Setter methods of OpenXmlElement
|Method|Meaning|
|---|---|
|PrependChild<T>(T)|Prepend a child|
|AppendChild<T>(T)|Append a child|
|Append(IEnumerable<OpenXmlElement>)|Append children|
|RemoveChild<T>(T)|Remove a child|
|RemoveAllChildren<T>()|Remove all children|
|ReplaceChild<T>(OpenXmlElement, T)|Replace a child|
  
##### OOXML (Office Open XML) vs Office Primary Interop Assembly (PIA)
###### Advantage of OOXML (Disadvantage of PIA)
* Create a Word/Excel using OOXML does not load pre-installed add-ins because OOXML just creates a text file (XML). Even if a pre-installed add-in is to crash, you can safely create a Word/Excel using OOXML.

###### Advantage of PIA (Disadvantage of OOXML)
* PIA offers properly structured building blocks of Excel/Word. If you combine building blocks of PIA in an incorrect structure, you can notice your mistake at a build time. In contrast, OOXML only offers building blocks of Excel/Word with no structure. Using OOXML, you never know at a build time whether building blocks you are combining is in the proper structure.
