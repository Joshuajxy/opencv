## OpenCV: Open Source Computer Vision Library


### Resources

* Homepage: <https://opencv.org>
  * Courses: <https://opencv.org/courses>
* Docs: <https://docs.opencv.org/4.x/>
* Q&A forum: <https://forum.opencv.org>
  * previous forum (read only): <http://answers.opencv.org>
* Issue tracking: <https://github.com/opencv/opencv/issues>
* Additional OpenCV functionality: <https://github.com/opencv/opencv_contrib>
* Donate to OpenCV: <https://opencv.org/support/>


### Contributing

Please read the [contribution guidelines](https://github.com/opencv/opencv/wiki/How_to_contribute) before starting work on a pull request.

#### Summary of the guidelines:

* One pull request per issue;
* Choose the right base branch;
* Include tests and documentation;
* Clean up "oops" commits before submitting;
* Follow the [coding style guide](https://github.com/opencv/opencv/wiki/Coding_Style_Guide).

### Additional Resources

* [Submit your OpenCV-based project](https://form.jotform.com/233105358823151) for inclusion in Community Friday on opencv.org
* [Subscribe to the OpenCV YouTube Channel](http://youtube.com/@opencvofficial) featuring OpenCV Live, an hour-long streaming show
* [Follow OpenCV on LinkedIn](http://linkedin.com/company/opencv/) for daily posts showing the state-of-the-art in computer vision & AI
* [Apply to be an OpenCV Volunteer](https://form.jotform.com/232745316792159) to help organize events and online campaigns as well as amplify them
* [Follow OpenCV on Mastodon](http://mastodon.social/@opencv) in the Fediverse
* [Follow OpenCV on Twitter](https://twitter.com/opencvlive)
* [OpenCV.ai](https://opencv.ai): Computer Vision and AI development services from the OpenCV team.


Comiple instructions to support freetype:

1.
sudo apt-get update
sudo apt-get install build-essential cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
sudo apt-get install libfreetype6-dev libpng-dev libjpeg-dev libtiff-dev libv4l-dev libxvidcore-dev libx264-dev
sudo apt-get install libgtk-3-dev
sudo apt-get install ffmpeg libavcodec-dev libavformat-dev libswscale-dev libavresample-dev

git clone https://github.com/opencv/opencv.git
git clone https://github.com/opencv/opencv_contrib.git

2.
cd opencv
mkdir build
cd build

3.
cmake -DOPENCV_EXTRA_MODULES_PATH=../../opencv_contrib/modules \
      -DBUILD_opencv_freetype=ON \
      -DBUILD_opencv_gapi=ON \
      -DBUILD_opencv_gapi_python_bindings_generator=ON \
      -DBUILD_opencv_java=OFF \
      -DBUILD_opencv_python3=ON \
      -DBUILD_opencv_python_bindings_generator=ON \
      -DBUILD_opencv_python_tests=OFF \
      -DWITH_GDAL=ON \
      -DWITH_GTK=ON \
      -DWITH_CUDA=OFF \
      -DWITH_TBB=ON \
      -DWITH_OPENCL=ON \
      -DWITH_OPENGL=ON \
      -DWITH_V4L=ON \
      -DWITH_QT=ON \
      -DWITH_IPP=ON \
      -DWITH_FFMPEG=ON \
      -DWITH_GSTREAMER=ON \
      -DWITH_1394=ON \
      -DWITH_OPENEXR=ON \
      -DWITH_TIFF=ON \
      -DWITH_WEBP=ON \
      -DWITH_JPEG=ON \
      -DWITH_PNG=ON \
      -DWITH_VTK=ON \
      -DWITH_LAPACK=ON \
      -DWITH_PROTOBUF=ON \
      -DWITH_EIGEN=ON \
      -DBUILD_PROTOBUF=ON \
      -DBUILD_PROTOBUF_PYTHON=ON \
      -DBUILD_PROTOBUF_LITE=OFF \
      -DBUILD_opencv_world=ON \
      -DCMAKE_INSTALL_PREFIX=/usr/local ..
4.
make -j$(nproc)
sudo make install
