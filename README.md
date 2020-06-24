## Libreria Onboarding
¡Saludos mi nombre es Jhelson, estudiante de Ingenieria de Sistemas!

Esta libreria permite ver 4 ventanas, a continuación veras una imagen ejemplo de como es:
 ![FVCproductions](https://pickaso.com/wp-content/uploads/2017/09/onboarding-tutorial-app.jpg)
 
-------------------------------------------------------------------------------------------------

### Requisitos de editor

Android Studio

### Pasos para la instalación de la libreria:

## Paso 1.-

Agregue el repositorio JitPack a su archivo de compilación
Agréguelo en su raíz build.gradle al final de los repositorios:

allprojects 
{
		repositories
    {
			...
			maven { url 'https://jitpack.io' }
		}
}

## Paso 2.-
  
  Agregar la dependencia
  dependencies 
  {
	        implementation 'com.github.jhelson99:OnboardingLib:1.0.1'
	}
   


## Código para la implementación en un nuevo proyecto (MainActivity.java):

    private ViewPager viewPagerContainer;

    @Override
    protected void onCreate(Bundle savedInstanceState)
    {
        super.onCreate(savedInstanceState);
        setContentView(com.jhelsoncarrillo.mylibraryonboarding.R.layout.activity_main);

        //initializeComponents
        _initializeComponents();

        //initializeAdapter
        _initializeFragmentAdapter();
    }

    public void _initializeComponents()
    {
        viewPagerContainer = findViewById(com.jhelsoncarrillo.mylibraryonboarding.R.id.viewPagerContainer);
    }

    public void _initializeFragmentAdapter()
    {
        OnboardingAdapter adapter = new OnboardingAdapter(getSupportFragmentManager());
        viewPagerContainer.setAdapter(adapter);
    }
    
## Código para la implementación en un nuevo proyecto (activity_main.xml):

<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <androidx.viewpager.widget.ViewPager
        android:id="@+id/viewPagerContainer"
        android:layout_width="match_parent"
        android:layout_height="match_parent">
    </androidx.viewpager.widget.ViewPager>

</LinearLayout>
