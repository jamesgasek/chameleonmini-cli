
# Crane Cab Driver

Recieves & logs  TCP streams from the hook block.



## Connection Reference


| Connection        |       Type     | Description                |
| :---------------- | :------------- | :------------------------- |
| `192.168.10.5::1` | `double`       | A stream of lidar readings obtained by the ILR2250 lidar |



| Connection          |        Type            | Description                       |
| :------------------ | :--------------------- | :-------------------------------- |
| ``192.168.10.5::2`` | `std::vector<uint8_t>` | raw JPEG data, compressed capture of the BASLER camera. 1024x1024 |

| Connection          |        Type            | Description                       |
| :------------------ | :--------------------- | :-------------------------------- |
| ``192.168.10.5::3`` | `sbg_ellipse_d::position` | Contains the position data in a struct defined in the SBG hardware class. |


| Connection          |        Type            | Description                       |
| :------------------ | :--------------------- | :-------------------------------- |
| ``192.168.10.5::4`` | `sbg_ellipse_d::heading` | contains the HDT heading data in a struct defined in the SBG hardware class. |

| Connection          |        Type            | Description                       |
| :------------------ | :--------------------- | :-------------------------------- |
| ``192.168.10.5::5`` | `sbg_ellipse_d::attitude` |EKF Attitude data (roll, pitch, yaw). Calculated using IMU and GPS data  |

| Connection          |        Type            | Description                       |
| :------------------ | :--------------------- | :-------------------------------- |
| ``192.168.10.5::6`` | `std::string` | GGA statements coming from the SBG device.  |

## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

`STEEL_EYE_ROOT_DIR="/usr/local/src/Structural-Services-Startup"`
`STEEL_EYE_LIB_ROOT_DIR="/usr/local/src/Steel-Eye-Libraries/desktop"`
`CMAKE_PREFIX_PATH="/usr/local/src/Steel-Eye-Libraries/desktop/Boost/boost_1_75_0/"`
`CMAKE_PREFIX_PATH="$CMAKE_PREFIX_PATH:/usr/local/src/Steel-Eye-Libraries/desktop/pylon6/"`
`CMAKE_PREFIX_PATH="$CMAKE_PREFIX_PATH:/usr/local/src/Steel-Eye-Libraries/desktop/pylon6/include/"`
`CMAKE_PREFIX_PATH="$CMAKE_PREFIX_PATH:/usr/local/src/Steel-Eye-Libraries/desktop/opencv-nocuda/lib/cmake/opencv4/"`
`CMAKE_PREFIX_PATH="$CMAKE_PREFIX_PATH:/usr/local/src/Steel-Eye-Libraries/desktop/ifc++/IfcPlusPlus/src/"`
`CMAKE_PREFIX_PATH="$CMAKE_PREFIX_PATH:/usr/local/src/Steel-Eye-Libraries/desktop/sFoundation2/"`
`CMAKE_PREFIX_PATH="$CMAKE_PREFIX_PATH:/usr/local/src/Steel-Eye-Libraries/desktop/ebus_sdk/"`
`MEDAQLIB_ROOT="/usr/local/src/Steel-Eye-Libraries/desktop/MEDAQLIB"`
`IFCPP_ROOT="/usr/local/src/Steel-Eye-Libraries/desktop/ifc++"`
`GENICAM_ROOT_V3_3="/usr/local/src/Steel-Eye-Libraries/desktop/ebus_sdk/lib/genicam"`



## Building

Build using CMAKE
```bash
mkdir build
cd build
cmake ..
cmake --build .
```
    
## Running

```bash
  sudo ./crane_cab_driver
```

# chameleonmini-cli
