# dlib_ros
ROS Wrapper for Dlib, with some minor improvements

## Improvements
- Use std::bitset (fixed at 256-bit) instead of boost::dynamic_bitset<> for performance boost in BRIEF descriptor calculation ( the `distance()` function particularly)
- Add cv::lineTypes in the drawing functions
- fix the compiler warning on unused variables
