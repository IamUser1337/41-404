If an underlying API doesn't support webhooks, polling triggers can be a good alternative. They can be implemented by using standard retrieve methods that support result filtering, such as List Invoices, after a certain date.  

The system will call your API regularly to check for changes in the data. The polling interval is controlled by the system and is usually around two minutes. Polling triggers also support batch result processing that could be beneficial for processing large volumes of changes. 

The following video demonstrates how to add a polling trigger to the WooCommerce custom connector that was created previously. 

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyYqC]