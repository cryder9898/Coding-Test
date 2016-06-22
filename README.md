![Screenshot](http://i.imgur.com/B7Jn4CU.png)

##Use of flavors to share code-base with multiple projects.
We can make use of the Gradle capabilities to share the same-code base in different projects. The Android Studio IDE has complete support for this, and changing the Build Variants and accessing this information from the Java code is trivial.

##Picasso for Image loading.
Picasso will handle the caching, lazy loading, error handler and placeholder setup for us and requires a quick and seamless setup. The only challenge we might face when working with is the cropping and correct orientation inside a lazy-loaded container, like in a ViewHolder pattern inside a RecyclerView (this is slightly more challenging but solvable situation).
 
##Use of fragments to support multiple dimensions.
Android best practices mention the use of Fragments to support multiple screen sizes in the main developer’s page. We’re able to detect the dimensions with the built-in layout Inflater that will detect if we have different sets of layouts for different screens (for example this folders layout and layout-w600dp, the former will be the layouts that will be inflated by default, the latest will be the container for the layouts with a larger width than 600dp). You can also calculate the current width with the DisplayMetrics class and make the validation by yourself (not recommended).

##Retrofit to consume APIs.
Retrofit is a HTTP client that has built-in support for multiple JSON to POJO converters, like GSON, Jackson, Moshi, Wire and others. In the end it will save a lot of boilerplate code writing and will make the classes easier to read, it handles the HTTP requests with simple interfaces that support different URLs parameters, it also has support for HTTP interceptors and other plug-ins.

##GSON to make the JSON to POJO conversion.
Retrofit has a built-in support for multiple JSON to POJO conversion, one of the simplest is GSON, you just have to set a few annotations in the actual Java class and add a single line in your Retrofit instance builder and you are all set, ready to read all the information coming from your API in your classes.

##Butterknife to do the View lookups.
Butterknife is a library that helps you avoid the boilerplate code (findViewById calls), it does it doing code injection, this means that does the lookup at runtime, it will also give you the capabilities to listen for onClick events, so you also avoid creating onClickListeners in your Android components, the only part that might be challenging when using it is the use of Proguard (like with any other library with code-injection).

##LeakCanary to detect memory leaks.
The Android system by itself has limited memory usage, it is mostly shared by multiple components, so it is very common to have OutOfMemory errors, so we need to keep track of every single reference and its usages in our code, that might be some-kind difficult when working with a lot of classes, LeakCanary uses the Garbage Collector extensions in Android to check if a reference has lived longer than it should (by calculating time offsets between calls), and then provides easy (kind of) to read reports on the actual references and the objects that we’re not successfully collected by the system gc.

##RecyclerView to handle multiple item showing.
The RecyclerView is a new and more powerful ListView, it allows you to have different capabilities that were difficult to implement with normal item Scrolling views, like: Item animators, item decorators, easier to implement ViewHolder pattern, custom adapters and custom LayoutManagers (that give you grid, staggered grid or simple linear and horizontal behaviors).

##RecyclerView animations to improve User Interface
User Interaction is vital for an app success, so it is important to have the designs of the UI and UX above expectations, a simple animation when a View is shown in the screen might be the turning point.

##DrawerLayout to handle a small menu
It might be used to put different views and menu items in a separate and elegant popup, it was first introduced in the after Material Design days, and it’s helped a lot of applications to handle user sessions and organize multiple items.

##Use of AsyncTask to handle networking connections
It is important for the user experience and for the app-living-state that all the long time-consuming operations are done in a different thread that the main one (UI thread), it is also bad to believe that ANY network operation will be quick in Android (even non-trivial to assume that the network connection will always be available), so it is better to just go with a simple Android framework that gives you all the capabilities to send Messages between the threads with built-in methods.
