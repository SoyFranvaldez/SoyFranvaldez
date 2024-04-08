  BlockstoreClient client = Blockstore.getClient(this);
  byte[] bytes1 = new byte[] { 1, 2, 3, 4 };  // Store one data block.
  String key1 = "com.example.app.key1";
  StoreBytesData storeRequest1 = StoreBytesData.Builder()
          .setBytes(bytes1)
          // Call this method to set the key value pair the data should be associated with.
          .setKeys(Arrays.asList(key1))
          .build();
  client.storeBytes(storeRequest1)
    .addOnSuccessListener(result -> Log.d(TAG, "stored " + result + " bytes"))
    .addOnFailureListener(e -> Log.e(TAG, "Failed to store bytes", e));
