
```kts
pluginManagement {  
    repositories {  
        maven { url = uri("https://maven.aliyun.com/repository/google") }  
        maven { url = uri("https://maven.aliyun.com/repository/jcenter") }  
        maven { url = uri("https://maven.aliyun.com/repository/gradle-plugin") }  
    }  
}  
dependencyResolutionManagement {  
    repositoriesMode.set(RepositoriesMode.FAIL_ON_PROJECT_REPOS)  
    repositories {  
        maven { url = uri("https://maven.aliyun.com/repository/google") }  
        maven { url = uri("https://maven.aliyun.com/repository/jcenter") }  
        maven { url = uri("https://maven.aliyun.com/repository/gradle-plugin") }  
    }  
}  
  
rootProject.name = "demo4"
```