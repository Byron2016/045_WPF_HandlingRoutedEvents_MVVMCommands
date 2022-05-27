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
	
	- Crear carpeta Models
		- Agregar clase ObservableObject
			- Esta clase hereda de INotifyPropertyChanged y hay que implementarla.
			- Agregar un método OnPropertyChanged.

		- Agregar clase TodoItem
			- Esta clase guardará el modelo de datos.
			
	- Crear carpeta ViewModels
		- Crear clase MainViewModel que hereda de ObservableObject
		- Crear en MainView.xaml.cs un DataContext al MainViewModel
			- DataContext = new MainViewModel();
		- Crear clase TodoListViewModel que hereda de ObservableObject
		
	- Agregar propfull _todoListViewModel a MainViewModel 
	- Agregar propfull _todoItems a TodoListViewModel
		- Es del tipo ObservableCollection<TodoItem>
	- Agregar UserControl Views/TodoList.xaml
		- Será el encargado de deslplegar la información.
	- Agregar a mainView
		- UserControl
		- Ligarlo al DataContext TodoListViewModel
		
	- Agregar carpeta Commands
		- Agregar clase LoadTodoItemsCommand que implementa ICommand
		- Esta llenará el modelo.
		
	- Declarar LoadTodoItemsCommand en TodoListViewModel
		- Llamarlo en el constructor.