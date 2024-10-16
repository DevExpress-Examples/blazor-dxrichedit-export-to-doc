<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/523327013/24.1.3%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/T1108444)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
[![](https://img.shields.io/badge/💬_Leave_Feedback-feecdd?style=flat-square)](#does-this-example-address-your-development-requirementsobjectives)
<!-- default badges end -->
# Blazor Rich Text Editor - How to export a document to a file (DOC format)

This example adds a custom button to the **Download** menu on the **File** tab. Click this button to export an open document to a file (DOC format) and save it in the project folder.

![Blazor DxRichEdit export a document to the DOC format](/images/export-to-doc.png)

Our Blazor [Rich Text Editor](https://docs.devexpress.com/Blazor/401891/rich-text-editor) supports the following document formats: DOCX, RTF, TXT, and HTML. You can use the [RichEditDocumentServer](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditDocumentServer) component to import and export documents in DOC format. To add this component to your application, install the [DevExpress.RichEdit.Core](https://nuget.devexpress.com/packages/DevExpress.RichEdit.Core/) package.

The [CustomizeRibbon](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit.CustomizeRibbon) event allows you to access and customize the Rich Text Editor's built-in ribbon UI. Call the [AddCustomButton](https://docs.devexpress.com/Blazor/DevExpress.Blazor.Office.BarItemCollection.AddCustomButton(System.String-System.Func-System.Threading.Tasks.Task-)) in the event handler to add a custom button to the ribbon. Execute the following actions in response to the click event to export the open document to a file (DOC format):

1. [Save](https://docs.devexpress.com/Blazor/DevExpress.Blazor.RichEdit.DxRichEdit.SaveDocumentAsync(System.Threading.CancellationToken)) the open document's content.
2. Initialize a new instance of the [RichEditDocumentServer](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditDocumentServer) class.
3. [Load](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditDocumentServer.LoadDocument(System.Byte--)) document content to the document server.
4. *(Optional)* Customize the document server's [export options](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditControlOptionsBase.Export).
5. [Save](https://docs.devexpress.com/OfficeFileAPI/DevExpress.XtraRichEdit.RichEditDocumentServer.SaveDocument(DevExpress.XtraRichEdit.DocumentFormat)) the document to a file (DOC format).
6. Use the [downloadFileFromStream](https://learn.microsoft.com/en-us/aspnet/core/blazor/file-downloads#download-from-a-stream) JS function to download the file.

## Files to Look At

- [Index.razor](./CS/ExportToDoc/Pages/Index.razor)
- [Index.razor.js](./CS/ExportToDoc/Pages/index.razor.js)

## Documentation

- [Document Management in the Rich Text Editor](https://docs.devexpress.com/Blazor/403344/rich-edit/document-management)
- [Rich Text Editor Examples](https://docs.devexpress.com/Blazor/403343/rich-edit/examples)
- [Word Processing Document API](https://docs.devexpress.com/OfficeFileAPI/17488/word-processing-document-api)
 
## More Examples

- [Blazor Rich Text Editor - How to implement custom document save capabilities](https://github.com/DevExpress-Examples/blazor-dxrichedit-custom-saving)
<!-- feedback -->
## Does this example address your development requirements/objectives?

[<img src="https://www.devexpress.com/support/examples/i/yes-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=blazor-dxrichedit-export-to-doc&~~~was_helpful=yes) [<img src="https://www.devexpress.com/support/examples/i/no-button.svg"/>](https://www.devexpress.com/support/examples/survey.xml?utm_source=github&utm_campaign=blazor-dxrichedit-export-to-doc&~~~was_helpful=no)

(you will be redirected to DevExpress.com to submit your response)
<!-- feedback end -->
