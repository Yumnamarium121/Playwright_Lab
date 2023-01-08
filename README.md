# Playwright_Lab
practice code for playwright
using Microsoft.Playwright;

namespace Lab33_Assignment
{
    
    public class Widgets
    {
        
        public async Task WidgetInteraction()
        {
            var playwright = await Playwright.CreateAsync();

            var browser = await playwright.Chromium.LaunchAsync(new BrowserTypeLaunchOptions
            { Headless = false, SlowMo = 50, });

            var context = await browser.NewContextAsync();

            await context.Tracing.StartAsync(new()
            {
                Screenshots = true,
                Snapshots = true,
                Sources = true
            });

            var Page = await context.NewPageAsync();


            await Page.GotoAsync("https://demoqa.com/");

            await Page.Locator("div:nth-child(4) > div > .card-up").ClickAsync();

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Accordian" }).ClickAsync();

            await Page.GetByText("What is Lorem Ipsum?").ClickAsync();

            await Page.GetByText("Where does it come from?").ClickAsync();

            await Page.GetByText("Where does it come from?").ClickAsync();

            await Page.GetByText("Why do we use it?").ClickAsync();

            await Page.GetByText("Why do we use it?").ClickAsync();

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Auto Complete" }).ClickAsync();

            await Page.Locator(".auto-complete__value-container").First.ClickAsync();

            await Page.Locator("#autoCompleteMultipleInput").FillAsync("blac");

            await Page.Locator("#autoCompleteMultipleInput").PressAsync("Enter");

            await Page.Locator("#autoCompleteMultipleInput").FillAsync("white");

            await Page.Locator("#autoCompleteMultipleInput").PressAsync("Enter");

            await Page.Locator("#autoCompleteMultipleInput").FillAsync("blue");

            await Page.Locator("#autoCompleteMultipleInput").PressAsync("Enter");

            await Page.Locator("#autoCompleteMultipleInput").FillAsync("yel");

            await Page.Locator("#autoCompleteMultipleInput").PressAsync("Enter");

            await Page.Locator("#autoCompleteMultipleInput").PressAsync("Tab");

            await Page.Locator("#autoCompleteSingleInput").FillAsync("bla");

            await Page.Locator("#autoCompleteSingleInput").PressAsync("Enter");

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Date Picker" }).ClickAsync();

            await Page.Locator("#datePickerMonthYearInput").ClickAsync();

            await Page.GetByRole(AriaRole.Combobox).First.SelectOptionAsync(new[] { "6" });

            await Page.GetByRole(AriaRole.Combobox).Nth(1).SelectOptionAsync(new[] { "1961" });

            await Page.GetByRole(AriaRole.Option, new() { NameString = "Choose Monday, July 10th, 1961" }).ClickAsync();

            await Page.Locator("#dateAndTimePickerInput").ClickAsync();

            await Page.GetByText("19:00").ClickAsync();

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Slider" }).ClickAsync();

            await Page.GetByRole(AriaRole.Slider).ClickAsync();

            await Page.GetByRole(AriaRole.Slider).ClickAsync();

            await Page.GetByText("50").ClickAsync();

            await Page.Locator("#sliderContainer div").First.ClickAsync();

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Progress Bar" }).ClickAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Start" }).ClickAsync();
            Thread.Sleep(11500);

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Tabs" }).ClickAsync();

            await Page.GetByRole(AriaRole.Tab, new() { NameString = "Origin" }).ClickAsync();

            await Page.GetByRole(AriaRole.Tab, new() { NameString = "Use" }).ClickAsync();

            await Page.GetByText("WhatOriginUseMore").ClickAsync();

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Tool Tips" }).ClickAsync();

            await Page.GetByPlaceholder("Hover me to see").ClickAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Hover me to see" }).ClickAsync();

            await Page.GetByPlaceholder("Hover me to see").ClickAsync();

            await Page.GotoAsync("https://demoqa.com/menu");

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Main Item 1" }).ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Main Item 3" }).ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Main Item 2" }).ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "SUB SUB LIST »" }).ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Sub Sub Item 1" }).ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Main Item 3" }).ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Main Item 1" }).ClickAsync();

            await Page.GotoAsync("https://demoqa.com/select-menu");

            await Page.Locator("#withOptGroup div").Filter(new() { HasTextString = "Select Option" }).Nth(1).ClickAsync();

            await Page.Locator("#react-select-2-input").FillAsync("group 1, option 2");

            await Page.Locator("#react-select-2-input").PressAsync("Enter");

            await Page.Locator("#selectOne div").Filter(new() { HasTextString = "Select Title" }).Nth(1).ClickAsync();

            await Page.Locator("#react-select-3-input").FillAsync("prof");

            await Page.Locator("#react-select-3-input").PressAsync("Enter");

            await Page.Locator("#oldSelectMenu").SelectOptionAsync(new[] { "10" });

            await Page.Locator("div:nth-child(7) > .col-md-6 > .css-2b097c-container > .css-yk16xz-control > .css-1hwfws3").ClickAsync();

            await Page.Locator("#react-select-4-input").FillAsync("gre");

            await Page.Locator("#react-select-4-input").PressAsync("Enter");

            await Page.Locator("#react-select-4-input").FillAsync("bla");

            await Page.Locator("#react-select-4-input").PressAsync("Enter");

            await Page.Locator("#react-select-4-input").FillAsync("re");

            await Page.Locator("#react-select-4-input").PressAsync("Enter");

            await Page.Locator("#react-select-4-input").FillAsync("bl");

            await Page.Locator("#react-select-4-input").PressAsync("Enter");

            await Page.Locator("#cars").SelectOptionAsync(new[] { "audi" });
            await Page.Locator("#cars").SelectOptionAsync(new[] { "opel" });




            await context.Tracing.StopAsync(new()
            {
                Path = "Widgets_DemoQA.zip"
            });

            Thread.Sleep(5000);

            await context.CloseAsync();
            await browser.CloseAsync();

        }

    [TestClass]
    public class DemoqaTC
    {
        [TestMethod]
        public async Task A_Elements()
        {
            Elements elements = new Elements();
            await elements.TextBox();
            await elements.Checkbox();
            await elements.RadioButton();
            await elements.WebTables();
            await elements.Buttons();
        }

        [TestMethod]
        public async Task B_PracFill()
        {
            PracticeForm practiceForm = new PracticeForm();
            await practiceForm.FillForm();
        }

        [TestMethod]
        public async Task C_AlertWindows()
        {
            AlertWindwos alertWindwos = new AlertWindwos();
            await alertWindwos.Alerts();
        }

        [TestMethod]
        public async Task D_Widgets()
        {
            Widgets widgets = new Widgets();
            await widgets.WidgetInteraction();
        }

        
    
    public class AlertWindwos
    {
        
        public async Task Alerts()
        {
            var playwright = await Playwright.CreateAsync();

            var browser = await playwright.Chromium.LaunchAsync(new BrowserTypeLaunchOptions
            { Headless = false, SlowMo = 50, });

            var context = await browser.NewContextAsync();

            await context.Tracing.StartAsync(new()
            {
                Screenshots = true,
                Snapshots = true,
                Sources = true
            });

            var Page = await context.NewPageAsync();

            await Page.GotoAsync("https://demoqa.com/alerts");

            void Page_Dialog6_EventHandler(object sender, IDialog dialog)
            {
                Console.WriteLine($"Dialog message: {dialog.Message}");
                dialog.DismissAsync();
                Page.Dialog -= Page_Dialog6_EventHandler;
            }
            Page.Dialog += Page_Dialog6_EventHandler;
            await Page.Locator("#alertButton").ClickAsync();

            await Page.Locator("#timerAlertButton").ClickAsync();

            void Page_Dialog8_EventHandler(object sender, IDialog dialog)
            {
                Console.WriteLine($"Dialog message: {dialog.Message}");
                dialog.DismissAsync();
                Page.Dialog -= Page_Dialog8_EventHandler;
            }
            Page.Dialog += Page_Dialog8_EventHandler;
            await Page.Locator("#confirmButton").ClickAsync();

            await Page.GetByRole(AriaRole.List).Locator("#item-2").GetByText("Frames").ClickAsync();

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Nested Frames" }).ClickAsync();

            await Page.FrameLocator("#frame1").FrameLocator("iframe").GetByText("Child Iframe").ClickAsync();

            await Page.FrameLocator("#frame1").FrameLocator("iframe").Locator("html").ClickAsync();

            await Page.FrameLocator("#frame1").GetByText("Parent frame").ClickAsync();

            await Page.FrameLocator("#frame1").GetByText("Parent frame").ClickAsync();

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Modal Dialogs" }).ClickAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Small modal" }).ClickAsync();

            await Page.Locator("#closeSmallModal").ClickAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Large modal" }).ClickAsync();

            await Page.Locator("#closeLargeModal").ClickAsync();


            await context.Tracing.StopAsync(new()
            {
                Path = "AlertWindows_DemoQA.zip"
            });

            Thread.Sleep(5000);

            await context.CloseAsync();
            await browser.CloseAsync();

        }
 public class Elements
    {
        
        public async Task TextBox()
        {
            var playwright = await Playwright.CreateAsync();

            var browser = await playwright.Chromium.LaunchAsync(new BrowserTypeLaunchOptions
            { Headless = false, SlowMo = 50, });

            var context = await browser.NewContextAsync();

            await context.Tracing.StartAsync(new()
            {
                Screenshots = true,
                Snapshots = true,
                Sources = true
            });



            var Page = await context.NewPageAsync();

            await Page.GotoAsync("https://demoqa.com/elements");

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Text Box" }).ClickAsync();

            await Page.GetByPlaceholder("Full Name").ClickAsync();

            await Page.GetByPlaceholder("Full Name").FillAsync("Khan Baba");

            await Page.GetByPlaceholder("Full Name").PressAsync("Tab");

            await Page.GetByPlaceholder("name@example.com").FillAsync("MullaTester@yopmail.com");

            await Page.GetByPlaceholder("name@example.com").PressAsync("Tab");

            await Page.GetByPlaceholder("Current Address").FillAsync("Hotel 5, Street 4, Avenue Creek, Optar");

            await Page.GetByPlaceholder("Current Address").PressAsync("Tab");

            await Page.Locator("#permanentAddress").FillAsync("Hotel 5, Street 5 , Avenue Creek, Optar");

            await Page.Locator("#permanentAddress").PressAsync("Tab");

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Submit" }).PressAsync("Enter");

            await Page.GetByText("Permananet Address :Hotel 5, Street 5 , Avenue Creek, Optar").ClickAsync();



            await context.Tracing.StopAsync(new()
            {
                Path = "Textbox_DemoQA.zip"
            });

            Thread.Sleep(5000);

            await context.CloseAsync();
            await browser.CloseAsync();

        }


        public async Task Checkbox()
        {
            var playwright = await Playwright.CreateAsync();

            var browser = await playwright.Chromium.LaunchAsync(new BrowserTypeLaunchOptions
            { Headless = false, SlowMo = 50, });

            var context = await browser.NewContextAsync();

            await context.Tracing.StartAsync(new()
            {
                Screenshots = true,
                Snapshots = true,
                Sources = true
            });


            var Page = await context.NewPageAsync();

            await Page.GotoAsync("https://demoqa.com/elements");

            await Page.GetByText("Check Box").ClickAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Toggle" }).ClickAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Toggle" }).Nth(1).ClickAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Toggle" }).Nth(2).ClickAsync();

            await Page.Locator("li:nth-child(3) > .rct-text > .rct-collapse").ClickAsync();

            await Page.Locator("label").Filter(new() { HasTextString = "Desktop" }).Locator("svg").First.ClickAsync();

            await Page.Locator("li:nth-child(2) > ol > li:nth-child(2) > .rct-text > .rct-collapse").ClickAsync();

            await Page.Locator("li:nth-child(2) > ol > li > .rct-text > .rct-collapse").First.ClickAsync();

            await Page.Locator("label").Filter(new() { HasTextString = "React" }).Locator("svg").First.ClickAsync();

            await Page.Locator("label").Filter(new() { HasTextString = "Angular" }).Locator("svg").First.ClickAsync();

            await Page.Locator("label").Filter(new() { HasTextString = "Private" }).Locator("svg").First.ClickAsync();

            await Page.Locator("label").Filter(new() { HasTextString = "Public" }).Locator("svg").First.ClickAsync();

            await Page.Locator("label").Filter(new() { HasTextString = "General" }).Locator("svg").First.ClickAsync();

            await Page.Locator("label").Filter(new() { HasTextString = "Excel File.doc" }).Locator("svg").First.ClickAsync();

            await Page.GetByText("excelFile").ClickAsync();


            await context.Tracing.StopAsync(new()
            {
                Path = "Checkbox_DemoQA.zip"
            });

            Thread.Sleep(5000);

            await context.CloseAsync();
            await browser.CloseAsync();

        }

        public async Task RadioButton()
        {
            var playwright = await Playwright.CreateAsync();

            var browser = await playwright.Chromium.LaunchAsync(new BrowserTypeLaunchOptions
            { Headless = false, SlowMo = 50, });

            var context = await browser.NewContextAsync();

            await context.Tracing.StartAsync(new()
            {
                Screenshots = true,
                Snapshots = true,
                Sources = true
            });


            var Page = await context.NewPageAsync();


            await Page.GotoAsync("https://demoqa.com/elements");

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Radio Button" }).ClickAsync();

            await Page.GetByText("Impressive").ClickAsync();

            await Page.GetByText("Yes").ClickAsync();

            await Page.GetByRole(AriaRole.Paragraph).GetByText("Yes").ClickAsync();



            await context.Tracing.StopAsync(new()
            {
                Path = "RadioButton_DemoQA.zip"
            });

            Thread.Sleep(5000);

            await context.CloseAsync();
            await browser.CloseAsync();

        }


        public async Task WebTables()
        {
            var playwright = await Playwright.CreateAsync();

            var browser = await playwright.Chromium.LaunchAsync(new BrowserTypeLaunchOptions
            { Headless = false, SlowMo = 50, });

            var context = await browser.NewContextAsync();

            await context.Tracing.StartAsync(new()
            {
                Screenshots = true,
                Snapshots = true,
                Sources = true
            });


            var Page = await context.NewPageAsync();

            await Page.GotoAsync("https://demoqa.com/elements");

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Web Tables" }).ClickAsync();

            await Page.GetByPlaceholder("Type to search").ClickAsync();

            await Page.GetByPlaceholder("Type to search").FillAsync("Alden");

            await Page.Locator("#basic-addon2").ClickAsync();

            await Page.Locator("#edit-record-2 path").ClickAsync();

            await Page.GetByPlaceholder("Salary").ClickAsync();

            await Page.GetByPlaceholder("Salary").FillAsync("56000");

            await Page.GetByPlaceholder("Age").ClickAsync();

            await Page.GetByPlaceholder("Age").FillAsync("34");

            await Page.GetByPlaceholder("name@example.com").ClickAsync();

            await Page.GetByPlaceholder("name@example.com").FillAsync("MullaTester@yopmail.com");

            await Page.GetByPlaceholder("First Name").ClickAsync();

            await Page.GetByPlaceholder("First Name").FillAsync("Khan");

            await Page.GetByPlaceholder("First Name").PressAsync("Tab");

            await Page.GetByPlaceholder("Last Name").FillAsync("Baba");

            await Page.GetByPlaceholder("Department").ClickAsync();

            await Page.GetByPlaceholder("Department").FillAsync("SQA");

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Submit" }).ClickAsync();

            await Page.GetByPlaceholder("Type to search").ClickAsync();

            await Page.GetByPlaceholder("Type to search").PressAsync("Control+a");

            await Page.GetByPlaceholder("Type to search").FillAsync("");

            await Page.GetByPlaceholder("Type to search").ClickAsync();

            await Page.Locator("#basic-addon2").ClickAsync();


            await context.Tracing.StopAsync(new()
            {
                Path = "WebTables_DemoQA.zip"
            });

            Thread.Sleep(5000);

            await context.CloseAsync();
            await browser.CloseAsync();

        }

        public async Task Buttons()
        {
            var playwright = await Playwright.CreateAsync();

            var browser = await playwright.Chromium.LaunchAsync(new BrowserTypeLaunchOptions
            { Headless = false, SlowMo = 50, });

            var context = await browser.NewContextAsync();

            await context.Tracing.StartAsync(new()
            {
                Screenshots = true,
                Snapshots = true,
                Sources = true
            });


            var Page = await context.NewPageAsync();


            await Page.GotoAsync("https://demoqa.com/elements");

            await Page.GetByRole(AriaRole.Listitem).Filter(new() { HasTextString = "Buttons" }).ClickAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Double Click Me" }).ClickAsync(new LocatorClickOptions
            {
                ClickCount = 3,
            });

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Right Click Me" }).ClickAsync(new LocatorClickOptions
            {
                Button = MouseButton.Right,
            });

            //await Page.Locator("#DkiIS").ClickAsync();

            await Page.GetByRole(AriaRole.List).Locator("#item-5").ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Created" }).ClickAsync();

            await Page.Locator("#linkResponse").GetByText("Created").ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "No Content" }).ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Moved" }).ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Bad Request" }).ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Unauthorized" }).ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Forbidden" }).ClickAsync();

            await Page.GetByRole(AriaRole.Link, new() { NameString = "Not Found" }).ClickAsync();

            Thread.Sleep(1000);
            await Page.GotoAsync("https://demoqa.com/dynamic-properties");

           
            Thread.Sleep(5000);
            await Page.GetByRole(AriaRole.Button, new() { NameString = "Will enable 5 seconds" }).ClickAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Color Change" }).ClickAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Visible After 5 Seconds" }).ClickAsync();




            await context.Tracing.StopAsync(new()
            {
                Path = "Buttons_DemoQA.zip"
            });

            Thread.Sleep(5000);

            await context.CloseAsync();
            await browser.CloseAsync();

        }
public class PracticeForm
    {
        
        public async Task FillForm()
        {
            var playwright = await Playwright.CreateAsync();

            var browser = await playwright.Chromium.LaunchAsync(new BrowserTypeLaunchOptions
            { Headless = false, SlowMo = 50, });

            var context = await browser.NewContextAsync();

            await context.Tracing.StartAsync(new()
            {
                Screenshots = true,
                Snapshots = true,
                Sources = true
            });



            var Page = await context.NewPageAsync();


            await Page.GotoAsync("https://demoqa.com/automation-practice-form");

            await Page.GetByPlaceholder("First Name").ClickAsync();

            await Page.GetByPlaceholder("First Name").FillAsync("Khan");

            await Page.GetByPlaceholder("First Name").PressAsync("Tab");

            await Page.GetByPlaceholder("Last Name").FillAsync("Baba");

            await Page.GetByPlaceholder("Last Name").PressAsync("Tab");

            await Page.GetByPlaceholder("name@example.com").FillAsync("MullaTester@yopmail.com");

            await Page.GetByText("Male").Nth(1).ClickAsync();

            await Page.GetByPlaceholder("Mobile Number").ClickAsync();

            await Page.GetByPlaceholder("Mobile Number").FillAsync("3216549879");

            await Page.GetByPlaceholder("Mobile Number").PressAsync("Tab");

            await Page.GetByRole(AriaRole.Combobox).First.SelectOptionAsync(new[] { "5" });

            await Page.GetByRole(AriaRole.Combobox).Nth(1).SelectOptionAsync(new[] { "2017" });

            await Page.GetByRole(AriaRole.Option, new() { NameString = "Choose Tuesday, June 6th, 2017" }).ClickAsync();

            await Page.Locator(".subjects-auto-complete__value-container").ClickAsync();

            await Page.Locator("#subjectsInput").FillAsync("Phy");

            await Page.Locator("#react-select-2-option-0").ClickAsync();

            await Page.GetByText("Sports").ClickAsync();

            await Page.GetByText("Music").ClickAsync();

            await Page.GetByPlaceholder("Current Address").ClickAsync();

            await Page.GetByPlaceholder("Current Address").FillAsync("Address of my home etc. nothing else");

            await Page.GetByPlaceholder("Current Address").PressAsync("Tab");

            await Page.Locator("#react-select-3-input").PressAsync("Enter");



            await context.Tracing.StopAsync(new()
            {
                Path = "PracticeFrom_DemoQA.zip"
            });

            Thread.Sleep(5000);

            await context.CloseAsync();
            await browser.CloseAsync();

        }

[TestClass]
    public class AdactinTC
    {
        [TestMethod]
        public async Task BookHotel()
        {
            Adactin adactin = new Adactin();
            await adactin.Booking();
        }
 public class Adactin
    {
        
        public async Task Booking()
        {
            var playwright = await Playwright.CreateAsync();

            var browser = await playwright.Chromium.LaunchAsync(new BrowserTypeLaunchOptions
            { Headless = false, SlowMo = 50, });

            var context = await browser.NewContextAsync();

            await context.Tracing.StartAsync(new()
            {
                Screenshots = true,
                Snapshots = true,
                Sources = true
            });



            var Page = await context.NewPageAsync();



            await Page.GotoAsync("https://adactinhotelapp.com/index.php");

            await Page.Locator("#username").ClickAsync();

            await Page.Locator("#username").FillAsync("Asadsdqwdwqd");

            await Page.Locator("#username").PressAsync("Tab");

            await Page.Locator("#password").FillAsync("kadmqo123");

            await Page.Locator("#password").PressAsync("Enter");

            await Page.Locator("#username").ClickAsync();

            await Page.Locator("#username").FillAsync("  ");

            await Page.Locator("#username").PressAsync("Enter");

            await Page.Locator("#username").PressAsync("Enter");

            await Page.Locator("#password").ClickAsync();

            await Page.Locator("#password").FillAsync("asds");

            await Page.Locator("#password").PressAsync("Enter");

            await Page.Locator("#username").ClickAsync();

            await Page.Locator("#username").FillAsync("MullaTester");

            await Page.Locator("#username").PressAsync("Tab");

            await Page.Locator("#password").FillAsync("MullaTester");

            await Page.Locator("#password").PressAsync("Enter");

            await Page.Locator("#location").SelectOptionAsync(new[] { "Melbourne" });

            await Page.Locator("#hotels").SelectOptionAsync(new[] { "Hotel Sunshine" });

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Search" }).ClickAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Cancel" }).ClickAsync();

            await Page.GetByRole(AriaRole.Cell, new() { NameString = "Search Hotel (Fields marked with Red asterix (*) are mandatory) Location* Hotels Room Type Number of Rooms* Check In Date* (dd/mm/yyyy) Check Out Date* (dd/mm/yyyy) Adults per Room* Children per Room Search Reset" }).GetByRole(AriaRole.Cell).Filter(new() { HasTextString = "- Select Hotel - Hotel Creek Hotel Sunshine Hotel Hervey Hotel Cornice" }).ClickAsync();

            await Page.Locator("#location").SelectOptionAsync(new[] { "Adelaide" });

            await Page.Locator("#hotels").SelectOptionAsync(new[] { "Hotel Hervey" });

            await Page.Locator("#room_type").SelectOptionAsync(new[] { "Super Deluxe" });

            await Page.GetByRole(AriaRole.Cell, new() { NameString = "Search Hotel (Fields marked with Red asterix (*) are mandatory) Location* Hotels Room Type Number of Rooms* Check In Date* (dd/mm/yyyy) Check Out Date* (dd/mm/yyyy) Adults per Room* Children per Room Search Reset" }).GetByRole(AriaRole.Cell).Filter(new() { HasTextString = "- Select Number of Rooms - 1 - One 2 - Two 3 - Three 4 - Four 5 - Five 6 - Six 7" }).ClickAsync();

            await Page.Locator("#room_nos").SelectOptionAsync(new[] { "4" });

            await Page.Locator("#datepick_in").ClickAsync();

            await Page.Locator("#datepick_in").ClickAsync();

            await Page.Locator("#datepick_out").ClickAsync();

            await Page.Locator("#datepick_out").ClickAsync();

            await Page.Locator("#datepick_out").PressAsync("ArrowRight");

            await Page.Locator("#datepick_out").PressAsync("ArrowLeft");

            await Page.Locator("#datepick_out").PressAsync("ArrowLeft");

            await Page.Locator("#datepick_out").PressAsync("ArrowLeft");

            await Page.Locator("#datepick_out").PressAsync("ArrowLeft");

            await Page.Locator("#datepick_out").PressAsync("ArrowLeft");

            await Page.Locator("#datepick_out").PressAsync("ArrowLeft");

            await Page.Locator("#datepick_out").PressAsync("ArrowLeft");

            await Page.Locator("#datepick_out").PressAsync("ArrowLeft");

            await Page.Locator("#datepick_out").FillAsync("04/01/2023");

            await Page.Locator("#adult_room").SelectOptionAsync(new[] { "2" });

            await Page.Locator("#child_room").SelectOptionAsync(new[] { "1" });

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Search" }).ClickAsync();

            await Page.Locator("#radiobutton_0").CheckAsync();

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Continue" }).ClickAsync();

            await Page.Locator("#first_name").ClickAsync();

            await Page.Locator("#first_name").FillAsync("Khan");

            await Page.Locator("#first_name").PressAsync("Tab");

            await Page.Locator("#last_name").FillAsync("Baba");

            await Page.Locator("#last_name").PressAsync("Tab");

            await Page.Locator("#address").FillAsync("street1 avenue 5, lane 8");

            await Page.Locator("#address").PressAsync("Tab");

            await Page.Locator("#cc_num").FillAsync("3216549873216549");

            await Page.Locator("#cc_type").SelectOptionAsync(new[] { "MAST" });

            await Page.Locator("#cc_exp_month").SelectOptionAsync(new[] { "5" });

            await Page.GetByRole(AriaRole.Cell, new() { NameString = "Back Book A Hotel Hotel Name Location Room Type Number of Rooms Total Days Price per Night Total Price GST Final Billed Price First Name* Last Name* Billing Address* Credit Card No.* Use 16 digit Dummy Data Credit Card Type* Expiry Date* CVV Number* Book Now Cancel" }).GetByRole(AriaRole.Row, new() { NameString = "CVV Number*" }).GetByRole(AriaRole.Cell).Nth(1).ClickAsync();

            await Page.Locator("#cc_exp_year").SelectOptionAsync(new[] { "2016" });

            await Page.Locator("#cc_cvv").ClickAsync();

            await Page.Locator("#cc_cvv").FillAsync("687");

            await Page.GetByRole(AriaRole.Button, new() { NameString = "Book Now" }).ClickAsync();

            Thread.Sleep(5000);

            //await Page.GotoAsync("https://adactinhotelapp.com/BookingConfirm.php");

            await Page.GetByRole(AriaRole.Button, new() { NameString = "My Itinerary" }).ClickAsync();

            await context.Tracing.StopAsync(new()
            {
                Path = "AdactingBooking.zip"
            });

            Thread.Sleep(10000);

            await context.CloseAsync();
            await browser.CloseAsync();

        }
    }
}
