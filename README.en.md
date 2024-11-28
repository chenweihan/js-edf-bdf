# js-edf-bdf
JavaScript reader of EDF+/BDF+ files


该库基于https://github.com/Neurobotics/jsEDF开源项目

因为在测试中发现以上项目处理大文件，比如400M会奔溃，原因是fileReader.readAsDataURL() 读取大文件会返回空。

这项目做了优化：
1：由file文件流转base64,base64转ArrayBuffer，调整为直接file文件流转ArrayBuffer
2：大文件的file文件流进行了切换片读取，最终合并为ArrayBuffer

打开调试工具即可查看解析后的数据



The library is based on open source projects at https://github.com/Neurobotics/jsEDF

Because it was found in the test that the above project handles large files, such as 400M, it will crash because fileReader.readAsDataURL() will return empty when reading large files.

Open the debugging tool to view the parsed data

This project has been optimized:
1: The file file is transferred from base64 to ArrayBuffer and adjusted to ArrayBuffer for direct file flow
2: The file stream of large files is read by switching slices and eventually merged into ArrayBuffer