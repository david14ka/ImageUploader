# ImageUploader
ready to use upload image to server using retrofit2

	public void uploadimage() {
	
        final ProgressDialog dialog = new ProgressDialog(this);
        dialog.setTitle( "Uploads encours...");
        dialog.show();
		
        new ImageUploader.Uploader(this)
                .setBaseUrl("http://printemps.alwaysdata.net/link-cube/")
                .setImageBitmap(bitmap,100)
                .setImageName(UUID.randomUUID().toString())
                .upload(new ImageUploader.OnUploadImageCallback() {
                    @Override
                    public void onSuccess(String msg) {
                        Toast.makeText(UploadActivity.this, msg, Toast.LENGTH_SHORT).show();
                        dialog.dismiss();
                    }

                    @Override
                    public void onFailure(String errorMsg) {
                        Toast.makeText(UploadActivity.this, errorMsg, Toast.LENGTH_SHORT).show();
                        dialog.dismiss();
                    }
           });
    }


