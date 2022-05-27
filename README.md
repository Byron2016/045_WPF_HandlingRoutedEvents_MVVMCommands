# 045_WPF_HandlingRoutedEvents_MVVMCommands

- REFERENCIA
	- SingletonSean
		- Handling WPF Routed Events with MVVM Commands - EASY WPF (.NET Core)
			- https://www.youtube.com/watch?v=Cx6YE86XzYE&list=PLA8ZIAm2I03h8QW3JaGrDBf7cq7F-cT4O&index=2
			
	- Crear proyecto.
		- Crear un proyecto WPF Application
		- Copiar .gitattributes y .gitignore
		
	- Cambiar nombre del MainWindow
		- Archivos
			- App.xaml
				De 
					<Application .... StartupUri="MainWindow.xaml">
				
				A  
					<Application .... StartupUri="MainView.xaml">
			- MainWindow.xaml
				De 
					<Window x:Class="aab_EventCommandsMVVM.MainWindow"
					....
					Title="MainWindow" Height="450" Width="800">
					
				A 
					<Window x:Class="aab_EventCommandsMVVM.MainView"
					....
					Title="MainView" Height="450" Width="800">
			- MainWindow.xaml.cs
				De 
					namespace aab_EventCommandsMVVM
					{
						/// <summary>
						/// Interaction logic for MainWindow.xaml
						/// </summary>
						public partial class MainWindow : Window
						{
							public MainWindow()
							{
								InitializeComponent();
							}
						}
					}
					
				A  
					namespace aab_EventCommandsMVVM
					{
						/// <summary>
						/// Interaction logic for MainView.xaml
						/// </summary>
						public partial class MainView : Window
						{
							public MainView()
							{
								InitializeComponent();
							}
						}
					}
					
		- Renombrar archivos 
			- MainWindow.xaml y MainWindow.xaml.cs a MainView.xaml y MainView.xaml.cs
			
	- Crear folder Views y mover MainView a este folder
		- App.xaml
			De 
				StartupUri="MainView.xaml">
			A
				StartupUri="Views/MainView.xaml">
		- Views/MainView.xaml
			De 
				<Window x:Class="aab_EventCommandsMVVM.MainView"
			A
				<Window x:Class="aab_EventCommandsMVVM.Views.MainView"
		- Views/MainView.xaml.cs
			De 
				namespace aab_EventCommandsMVVM
			A
				namespace aab_EventCommandsMVVM.Views
	
