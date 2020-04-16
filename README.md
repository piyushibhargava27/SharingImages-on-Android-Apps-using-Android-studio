# ImageShare-on-Android-Apps
Share image/data on other Applications like Whatsapp, Gmail, Instagram etc.. via Android/Android studio.


MainActivity.java code : 
button.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                Uri uri = Uri.parse(Environment.getExternalStorageDirectory() + "/" + Environment.DIRECTORY_DCIM + "/Restored/xyz.jpg");
                Intent share = new Intent(Intent.ACTION_SEND);
                share.putExtra(Intent.EXTRA_STREAM, uri);
                share.putExtra(Intent.EXTRA_TEXT,"hey guys..!!!");
                share.setType("image/*");
                share.addFlags(Intent.FLAG_GRANT_READ_URI_PERMISSION);
                startActivity(Intent.createChooser(share, "Share image File"));;
            }
        });
    }

MainActivity.java code Explanation:
1. Here in Uri.parse we have to give our image path.
2. "Environment.getExternalStorageDirectory() + "/" + Environment.DIRECTORY_DCIM" is returning the path till my DCIM folder where our image    is. 
3. Further there is a createChooser which is allowing you to choose from specifc app you want to use.
4. If you want it to be specifically shared to an application you have to give its package name and startActivity again.
    intent.setPackage("com.whatsapp");
            startActivity(intent);


