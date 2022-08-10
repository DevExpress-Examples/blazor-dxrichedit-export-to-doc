<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/523327013/22.1.4%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T1108444)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
# Rich Edit for Blazor - How to export a document to the HTML

This example creates a custom button that exports an open document to the HTML and saves it to a file in the project folder.

![Blazor DxRichEdit export a document to the HTML](/images/export-to-html.png)

Currently the [Rich Text Editor](https://docs.devexpress.com/Blazor/401891/rich-text-editor) does not support the HTML format, but you can use the [RichEditDocumentServer](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditDocumentServer) component to export a document to the HTML. To add this component in your application, install the [DevExpress.RichEdit.Core](https://nuget.devexpress.com/packages/DevExpress.RichEdit.Core/) package.

Handle the [CustomizeRibbon](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit.CustomizeRibbon) event to access and customize the built-in ribbon. Call the [AddCustomButton](https://docs.devexpress.com/Blazor/DevExpress.Blazor.Office.BarItemCollection.AddCustomButton(System.String-System.Func-System.Threading.Tasks.Task-)) in the event handler to create a custom button. 

Perform the following actions on this button's click:

1. [Save](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit.SaveDocumentAsync(System.Threading.CancellationToken)) the open's document content.
2. Initialize a new instance of the [RichEditDocumentServer](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditDocumentServer) class.
3. [Load](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditDocumentServer.LoadDocument(System.Byte--)) content of an open document to the document server.
4. *(Optional)* Customize the document server's [export options](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditControlOptionsBase.Export).
5. Save the exported document.

## Files to Look At

- [Index.razor](./CS/ExportToHtml/Pages/Index.razor)

## Documentation

- [Document Management in the Rich Text Editor](https://docs.devexpress.com/Blazor/403344/rich-edit/document-management)
- [Rich Text Editor Examples](https://docs.devexpress.com/Blazor/403343/rich-edit/examples)
- [Word Processing Document API](https://docs.devexpress.com/OfficeFileAPI/17488/word-processing-document-api)
