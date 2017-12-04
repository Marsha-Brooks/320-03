ISTA-320, Cohort 3 

C# Step by Step, Chapter 25 December 3, 2017 

1. What is the purpose of the Universal Windows Platform? What was the name of the predecessor to UWP? 
UWP was developed to converge platforms and reduce the number of differences
The platform that was the predecessor to the UWP was the Windows Runtime (WinRT) 
 2. Describe in detail how the lifetime of a UWP app differs from a traditional desktop application.
The lifetime of a UWP app is somewhat different from that of a traditional desktop app. You should design apps that can run on devices such as smartphones to suspend execution when the user switches focus to another app and then to resume running when the focus returns. This approach can help to conserve resources and battery life on a constrained device. Windows might decide to close a suspended app if it determines that it needs to release system resources such as memory. When the app next runs, it should be able to resume where it left off. This means that you need to be prepared to manage app state information in your code, save it to hard disk, and restore it at the appropriate juncture.
 3. Describe wo ways you can set and modify the properties of controls. 
You can modify the properties of controls by using the Properties window or by typing the equivalent XAML markup into the XAML window.
4. Describe the two layout schemes of UWP apps that we constructed in class.
The two layout schemes we constructed in class were the TabularView and ColumnarView.
A 13 inch desktop screen and a smartphone screen view.
 5. Describe three ways you can use the Visual State Manager to adapt the layout of UWP apps 
Three ways to use the Visual State Manager to adapt the layout of UMP are to modify the layout of the page at run time, switch between views based on the height and width of the window or create several versions of the MainPage.xaml file, one for each device family. Each of these XAML files can be linked to the same code-behind (MainPage.xaml.cs) so that they all run the same code.
6. Describe how you can modify multiple properties of multiple controls with one document. How do you connect this modification document with your UWP application?
With UWP apps, you can define reusable styles. You can implement them as app-wide resources by creating a resource dictionary, and then they are available to all controls in all pages in an app. You can also define local resources that apply to only a single page in the XAML markup for that page
