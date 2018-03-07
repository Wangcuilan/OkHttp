# OkHttp
Android网络请求框架
 
 
使用说明：远程加载JitPack包

第一步，在项目根目录下的build.gradle里添加 maven { url "https://jitpack.io" }引用：
 
	allprojects {
		repositories {
			...
			maven { url 'https://jitpack.io' }
		}
	}
 
第二步，在项目的app模块下的build.gradle里加：

	dependencies {
	        compile 'com.github.Sen-1996:OkHttp:v1.0.0'
	}


 
请求示列：
 
 
1.一般的post请求

          OkHttp.post()
                .url(URLs.SYS_GETfILEVER)
                .addParam("key", "val")
                .addParam("key", "val")
                .success(new HttpSuccessCallBack() {
                    @Override
                    public void onResponse(String result) throws Exception {
                            //返回结果 result
                    }
                }).send();
                
                
2.get请求失败回调，参数为map集合

          OkHttp.get()
                .url(URLs.SYS_GETfILEVER)
                .addParams(new HashMap<String, Object>())
                .success(new HttpSuccessCallBack() {
                    @Override
                    public void onResponse(String result) throws Exception {
                        //返回结果 result
                    }
                }).error(new HttpErrorCallBack() {
                   @Override
                   public void haveErrors(Exception e) {
                  //用于处理失败操作
                   e.printStackTrace();
               }}).send();
