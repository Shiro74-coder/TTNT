# BÁO CÁO CÁ NHÂN (23110193)
# 1. Mục tiêu
Mục tiêu chính của dự án này là ứng dụng các kiến thức đã học trong môn Trí tuệ Nhân tạo vào việc giải quyết một bài toán cụ thể, ở đây là bài toán 8 ô chữ (8-puzzle). Thông qua việc xây dựng một chương trình phần mềm, dự án hướng đến các mục tiêu sau:
+ Hiện thực hóa các thuật toán tìm kiếm: Áp dụng lý thuyết vào thực tế bằng cách cài đặt và chạy thử nghiệm một loạt các thuật toán tìm kiếm đã được học. 
+ Trực quan hóa và minh họa quá trình giải: Xây dựng một giao diện đồ họa (GUI) cho phép người dùng theo dõi trực quan từng bước di chuyển và quá trình hoạt động của các thuật toán khi giải bài toán 8 ô chữ. Mục tiêu là làm rõ hơn cách thức các thuật toán này tìm kiếm lời giải và giúp củng cố hiểu biết về chúng.
+ Khám phá và so sánh hiệu năng thuật toán: Tạo ra một môi trường để thử nghiệm, đánh giá và so sánh hiệu quả của các thuật toán khác nhau. Việc so sánh này dựa trên các tiêu chí như số bước tìm ra lời giải, thời gian thực thi và các đặc điểm riêng của từng thuật toán khi áp dụng cho bài toán 8 ô chữ.
+ Tìm hiểu về tìm kiếm trong các môi trường phức tạp: Mở rộng ứng dụng sang các thuật toán được thiết kế cho các môi trường mà thông tin không đầy đủ. Cụ thể là tìm kiếm trong môi trường không quan sát được và quan sát được một phần, qua đó tìm hiểu về khái niệm 'trạng thái niềm tin' và cách nó được cập nhật.
+ Bước đầu tiếp cận Học tăng cường: Ứng dụng thử nghiệm thuật toán học tăng cường cơ bản (Q-learning) vào bài toán 8 ô chữ. Điều này nhằm mục đích có được cái nhìn ban đầu về cách một tác nhân (agent) có thể học để đưa ra quyết định tối ưu thông qua tương tác với môi trường.

Dự án này là một bài tập ứng dụng cá nhân nhằm củng cố kiến thức lý thuyết về Trí tuệ Nhân tạo và phát triển kỹ năng triển khai thuật toán thông qua việc xây dựng một công cụ tương tác và hữu ích cho việc học tập và thực hành từ đó xây dựng nền tảng cho bản thân sau này.
# 2. Nội dung
Dự án được xây dựng dựa trên ngôn ngữ Python với thư viện CustomTkinter cho giao diện người dùng. Cấu trúc chính bao gồm các thành phần sau, tập trung vào việc giải quyết và minh họa bài toán 8-puzzle thông qua nhiều thuật toán tìm kiếm khác nhau:
+ Giao diện: Cung cấp một cửa sổ trực quan sử dụng thư viện CustomTkinter để hiển thị bài toán 8-puzzle và các tương tác, giúp người dùng dễ dàng theo dõi và điều khiển quá trình giải đố.
+ Bảng điều khiển: Là khu vực chính để người dùng nhập liệu trạng thái bắt đầu/đích, lựa chọn từ một danh sách đa dạng các thuật toán tìm kiếm, điều chỉnh tham số và kiểm soát tốc độ hoặc dừng quá trình thực thi của thuật toán.
+ Hiển thị Kết quả và Thông tin: Hiển thị các thông báo trạng thái, các bước giải chi tiết của bài toán sau khi thuật toán hoàn thành, thời gian thực thi, và các thông tin đặc thù của từng thuật toán
+ Hiển thị Kết quả Nâng cao cho Môi trường Phức tạp: Cung cấp các cửa sổ hiển thị chuyên biệt (từ result_windows.py) để trình bày chi tiết kết quả của các thuật toán tìm kiếm trong môi trường không hoàn toàn quan sát được hoặc quan sát được một phần, làm rõ các khái niệm như "trạng thái niềm tin" và chuỗi hành động
# 2.1. Các thuật toán tìm kiếm không có thông tin
# 2.1.1. BFS
BFS là một thuật toán tìm kiếm duyệt đồ thị hoặc cây theo từng "mức" (level). Nó bắt đầu từ một nút gốc (trạng thái ban đầu) và khám phá tất cả các nút hàng xóm ở mức hiện tại trước khi chuyển sang các nút ở mức tiếp theo. Sử dụng một hàng đợi (queue) để quản lý các trạng thái sẽ duyệt và một tập hợp (set) để lưu các trạng thái đã duyệt, nhằm tìm đường đi từ trạng thái bắt đầu đến trạng thái đích. Điều này đảm bảo rằng nếu có lời giải, BFS sẽ tìm thấy lời giải có số bước di chuyển ít nhất. 

                            BFS 
![BFS](https://github.com/Shiro74-coder/TTNT/blob/main/BFS.gif)
# 2.2. Các thuật toán tìm kiếm có thông tin
# 2.3. Các thuật toán tìm kiếm cục bộ
# 2.4. Các thuật toán tìm kiếm trong môi trường có ràng buộc
# 2.5. Các thuật toán tìm kiếm trong môi trường phức tạp
# 2.6. Các thuật toán học tăng cường


                            UCS 

![UCS](https://github.com/Shiro74-coder/TTNT/blob/main/UCS.gif)

                            DFS 

![DFS](https://github.com/Shiro74-coder/TTNT/blob/main/DFS.gif)

                            IDDFS 

![IDDFS](https://github.com/Shiro74-coder/TTNT/blob/main/IDDFS.gif)

                            GREENDY 

![GREENDY](https://github.com/Shiro74-coder/TTNT/blob/main/Greedy.gif)

                            A*

![A*](https://github.com/Shiro74-coder/TTNT/blob/main/Astar.gif)

                            IDA*

![IDA*](https://github.com/Shiro74-coder/TTNT/blob/main/IDAstar.gif)

                            SIMPLE_HC

![SIMPLEHC](https://github.com/Shiro74-coder/TTNT/blob/main/SimpleHC.gif)

                            STEEPEST_HC
![STEEPEST_HC](https://github.com/Shiro74-coder/TTNT/blob/main/SteepestHC.gif)

                            STOCHASTIC
![Stochastic](https://github.com/Shiro74-coder/TTNT/blob/main/Stochastic.gif)

                            SIMULATED ANNEALING
![Simulated_Annealing](https://github.com/Shiro74-coder/TTNT/blob/main/Simulated_Annealing.gif)

                            BEAM 
![BeamSearch](https://github.com/Shiro74-coder/TTNT/blob/main/BeamSearch.gif)

                          Genetic_GA
![Genetic_GA](https://github.com/Shiro74-coder/TTNT/blob/main/Genetic_GA.gif)

                          And_Or_Search
![And_Or_Search](https://github.com/Shiro74-coder/TTNT/blob/main/and_or_search.gif)

                          Search_no_Observation
![And_Or_Search](https://github.com/Shiro74-coder/TTNT/blob/main/search_no_obs.gif)
