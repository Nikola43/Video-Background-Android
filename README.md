# Video-Background-Android

# How to use

## 1. Create a folder within drawable called 'raw'

## 2. Paste your video into the folder

## 3. Create VideoView instance
    private VideoView videoView;

## 4. Bind layout
    videoView = findViewById(R.id.videoView);

## 5. Create Uri instance inside onCreate method
    Uri uri = Uri.parse("android.resource://"+getPackageName()+"/"+R.raw.login_background);

## 6. Set set uri and play video
    videoView.setVideoURI(uri);
    videoView.start();

## 7. Set transparent status bar
    if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.LOLLIPOP) {
        getWindow().setFlags(WindowManager.LayoutParams.FLAG_LAYOUT_NO_LIMITS,
                             WindowManager.LayoutParams.FLAG_LAYOUT_NO_LIMITS);
    }

## 8. Play video on loop
    videoView.setOnCompletionListener(new MediaPlayer.OnCompletionListener() {
        @Override
        public void onCompletion(MediaPlayer mp) {
            videoView.start();
        }
    });

## 9. Start video again when onResume() method is called
    @Override
    protected void onResume() {
        super.onResume();
        videoView.start();
    }
