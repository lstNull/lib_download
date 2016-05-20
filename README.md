# lib_download
处理异步下载的库，包含图片下载和ormlite(马天宇的开源)，且全局公用一个线程池
虽然有默认的正在加载和加载失败的图片，但是还是可以打成jar包使用
支持本地和网络图片，路径格式示例为："http://img.blog.csdn.net/20160114230048304",//网络
    			"assets://anim.gif",
                "drawable://"+R.drawable.anim,//资源路径gif图
                	"file:///mnt/sdcard/paint.png",//sd卡
使用方法简单：BmLoader.load(uri, imageView);
对于特殊的需求可以使用回调自己处理：BmLoader.load(uri, imageView, new BackListener() {
                @Override
                public void onProcess(int percent) {
                    
                }

                @Override
                public void onSuccess(Bitmap bitmap, Movie movie) {

                }
            });
            
如果view使用或者继承download.imageLoader.view.GifMovieView这个类的话支持gif图，否则只能用回调自己自定义view实现。
如果使用类download.imageLoader.view.GifMovieView，调用方法更简单了：view.bind(uri)。
