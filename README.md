# Android Application Development - GPS Location Calculator

This project is an Android application that calculates the distance between two locations (start and stop) using the device's GPS.

## Project Structure

### 1. MainActivity.java
This is the main activity where the logic for capturing GPS coordinates and calculating distance is implemented.

- **FusedLocationProviderClient** is used to access the device's last known location.
- **Permissions** for accessing fine location are requested at runtime.
- Two buttons are used:
  - `Start` button to capture the starting location.
  - `Stop` button to capture the stopping location and calculate the distance between them.
- The distance is displayed on the screen in meters.

```java
// Example code snippet from MainActivity.java

btnStart.setOnClickListener(v -> { 
    fusedLocationClient.getLastLocation()
        .addOnSuccessListener(MainActivity.this, new OnSuccessListener<Location>() {
            @Override
            public void onSuccess(Location location) { 
                if (location != null) { 
                    startLocation = location; 
                    Toast.makeText(MainActivity.this, "Start location recorded!", Toast.LENGTH_SHORT).show(); 
                } 
            }
        });
});
