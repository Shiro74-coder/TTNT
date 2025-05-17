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
# 2.1.2. UCS
UCS là một thuật toán tìm kiếm duyệt đồ thị hoặc cây bằng cách luôn ưu tiên mở rộng nút trạng thái có chi phí đường đi tích lũy thấp nhất từ nút gốc (trạng thái ban đầu). Nó sử dụng một hàng đợi ưu tiên (priority queue) để quản lý các nút sẽ được duyệt, với độ ưu tiên được xác định bởi chi phí đường đi. Bắt đầu với một hàng đợi ưu tiên chứa nút gốc với chi phí đường đi là 0. Sử dụng một tập hợp (set) hoặc cấu trúc dữ liệu tương tự để lưu trữ các trạng thái đã được khám phá (expanded/visited) hoặc để cập nhật chi phí tốt hơn đến một nút đã có trong hàng đợi.
UCS luôn tìm thấy lời giải nếu có lời giải tồn tại, luôn tìm thấy lời giải có tổng chi phí đường đi thấp nhất.

                            UCS 
![UCS](https://github.com/Shiro74-coder/TTNT/blob/main/UCS.gif)
# 2.1.3. DFS
DFS Tìm kiếm theo Chiều sâu là một thuật toán duyệt hoặc tìm kiếm trên cây hoặc đồ thị. Khác với BFS, DFS ưu tiên đi "sâu" nhất có thể vào một nhánh của cây tìm kiếm trước khi quay lui để thử các nhánh khác. 
DFS thường sử dụng một ngăn xếp (stack) để lưu trữ các trạng thái sẽ được duyệt. Cơ chế "vào sau, ra trước" (LIFO) của ngăn xếp giúp thuật toán đi sâu vào một nhánh. Tương tự như các thuật toán tìm kiếm khác, cần có một cơ chế (thường là một tập hợp - set) để lưu trữ các trạng thái đã được khám phá nhằm tránh việc duyệt lại và các vòng lặp vô hạn.
Trong không gian trạng thái hữu hạn và không có vòng lặp (hoặc có cơ chế phát hiện vòng lặp), DFS sẽ tìm ra lời giải nếu có. Tuy nhiên, nếu không gian trạng thái là vô hạn hoặc không có cơ chế kiểm tra vòng lặp/độ sâu tối đa, DFS có thể đi vào một nhánh vô tận và không bao giờ tìm thấy lời giải ngay cả khi nó tồn tại. DFS không đảm bảo tìm ra lời giải nông nhất (có số bước ít nhất). Nó có thể tìm thấy một lời giải ở một nhánh rất sâu trong khi có một lời giải khác ngắn hơn ở một nhánh chưa được khám phá.

                            DFS 
![DFS](https://github.com/Shiro74-coder/TTNT/blob/main/DFS.gif)
# 2.1.4. IDDFS
IIDDFS (Tìm kiếm theo Chiều sâu Lặp) là một thuật toán tìm kiếm kết hợp những ưu điểm của Tìm kiếm theo Chiều sâu (DFS) về mặt không gian bộ nhớ và Tìm kiếm theo Chiều rộng (BFS) về mặt tính đầy đủ và tính tối ưu (khi chi phí bước là đồng nhất). IDDFS thực hiện một loạt các lượt tìm kiếm DFS với giới hạn độ sâu tăng dần. Nó bắt đầu với giới hạn độ sâu là 0, sau đó là 1, rồi 2, và cứ thế tiếp tục cho đến khi tìm thấy trạng thái đích.
Giống như BFS, IDDFS sẽ luôn tìm thấy lời giải nếu có (khi chi phí bước là đồng nhất), IDDFS sẽ tìm thấy lời giải nông nhất (có số bước ít nhất) đầu tiên vì nó thử các độ sâu theo thứ tự tăng dần.

                            IDDFS 
![IDDFS](https://github.com/Shiro74-coder/TTNT/blob/main/IDDFS.gif)
# 2.2. Các thuật toán tìm kiếm có thông tin
# 2.2.1. Greedy
Greedy Best-First Search là một thuật toán tìm kiếm có thông tin. Nó cố gắng tìm ra lời giải bằng cách ưu tiên mở rộng nút trạng thái mà nó "tin" rằng gần nhất với trạng thái đích, dựa trên một hàm đánh giá heuristic (h(n)). Thuật toán này chọn nút tiếp theo để mở rộng dựa trên việc nút đó có vẻ "hứa hẹn" nhất theo đánh giá của hàm heuristic. Nó không quan tâm đến chi phí đã bỏ ra để đến được nút hiện tại (khác với A*). Mục tiêu là nhanh chóng tiến về phía đích, nhưng điều này có thể dẫn đến việc đi vào các đường không tối ưu hoặc bị kẹt.
Greedy có thể đi vào một nhánh vô hạn hoặc bị kẹt trong các vòng lặp nếu không có cơ chế phát hiện lặp lại hiệu quả hoặc nếu không gian trạng thái có các "ngõ cụt" mà heuristic vẫn đánh giá là tốt. Trong không gian trạng thái hữu hạn và có kiểm tra lặp lại, nó sẽ tìm thấy lời giải nếu có. Vì chỉ dựa vào heuristic mà không xét chi phí đã đi, Greedy thường không tìm ra lời giải ngắn nhất hoặc có chi phí thấp nhất. Nó có thể bị "đánh lừa" bởi heuristic để đi theo một con đường có vẻ ngắn hạn tốt nhưng lại dài hơn về tổng thể.

                            GREEDY 
![GREENDY](https://github.com/Shiro74-coder/TTNT/blob/main/Greedy.gif)
# 2.2.2. A*
A* (A-star) là một thuật toán tìm kiếm có thông tin, được coi là sự mở rộng thông minh của thuật toán Dijkstra và kết hợp ưu điểm của UCS với việc sử dụng hàm heuristic như trong Greedy. Nó tìm đường đi từ nút bắt đầu đến nút đích có tổng chi phí ước tính thấp nhất.
A* đánh giá các nút (trạng thái) dựa trên một hàm đánh giá f(n), được tính bằng tổng của hai thành phần:
+ g(n): Chi phí thực tế để đi từ trạng thái ban đầu đến trạng thái n.
+ h(n): Chi phí ước tính (heuristic) để đi từ trạng thái n đến trạng thái đích.
  
Công thức: f(n)=g(n)+h(n)
A* luôn ưu tiên mở rộng nút có giá trị f(n) thấp nhất. Vì vậy A* sẽ luôn tìm thấy lời giải nếu có. Nó đảm bảo tìm ra lời giải có chi phí thấp nhất (tối ưu) nếu hàm heuristic h(n) là chấp nhận được (admissible). Nếu h(n) nhất quán, A* còn hiệu quả hơn vì nó không cần phải mở lại các nút đã đóng.

                            A*
![A*](https://github.com/Shiro74-coder/TTNT/blob/main/Astar.gif)
# 2.2.3. IDA*
IDA* (A* Lặp Sâu Dần) là một thuật toán tìm kiếm đồ thị kết hợp những ưu điểm của A* (sử dụng hàm f(n)=g(n)+h(n)) với ý tưởng lặp sâu dần của IDDFS. Mục tiêu chính của IDA* là tìm ra lời giải tối ưu trong khi vẫn duy trì được yêu cầu bộ nhớ thấp. Thay vì sử dụng một giới hạn độ sâu như IDDFS, IDA* sử dụng một ngưỡng chi phí cho hàm f(n). Nó thực hiện một loạt các lượt tìm kiếm theo chiều sâu. Trong mỗi lượt, nó chỉ mở rộng các nút có giá trị f(n) không vượt quá ngưỡng hiện tại.
IDA* đảm bảo tìm ra lời giải có chi phí thấp nhất nếu hàm heuristic h(n) là chấp nhận được.

                            IDA*
![IDA*](https://github.com/Shiro74-coder/TTNT/blob/main/IDAstar.gif)
# 2.2.4. Beam Search
Beam Search là một thuật toán tìm kiếm heuristic, có thể coi là một biến thể của Breadth-First Search nhưng tối ưu hóa hơn về mặt không gian bộ nhớ. Thay vì mở rộng tất cả các nút ở mỗi độ sâu như BFS, Beam Search chỉ giữ lại một số lượng giới hạn các nút "tốt nhất" ở mỗi mức, được gọi là "độ rộng chùm" (beam width), ký hiệu là w.
+ Ở mỗi bước (mức độ sâu), thuật toán tạo ra tất cả các trạng thái con của các trạng thái hiện tại trong "chùm".
+ Sau đó, nó sắp xếp tất cả các trạng thái con này dựa trên một hàm heuristic (tương tự như Greedy Best-First Search).
+ Chỉ có w trạng thái con tốt nhất (có giá trị heuristic thấp nhất) được giữ lại để tạo thành "chùm" cho bước tiếp theo. Các trạng thái khác sẽ bị loại bỏ (pruned).

Vì Beam Search loại bỏ các trạng thái ở mỗi bước, nó có thể loại bỏ luôn nhánh chứa lời giải (kể cả lời giải tối ưu). Tương tự như tính đầy đủ, việc cắt tỉa có thể khiến nó bỏ lỡ lời giải tối ưu.

                            BEAM SEARCH
![BeamSearch](https://github.com/Shiro74-coder/TTNT/blob/main/BeamSearch.gif)
# 2.3. Các thuật toán tìm kiếm cục bộ
# 2.3.1. Simple Hill Climbing
Simple Hill Climbing là một thuật toán tìm kiếm cục bộ. Nó hoạt động bằng cách liên tục di chuyển theo hướng "tốt hơn" trong không gian trạng thái, với hy vọng đạt đến một đỉnh (cục bộ hoặc toàn cục) tương ứng với lời giải. Đây là một thuật toán "tham lam" ở mức độ cục bộ.
+ Bắt đầu từ một trạng thái ban đầu.
+ Ở mỗi bước, xem xét các trạng thái "hàng xóm" (các trạng thái có thể đạt được bằng một hành động từ trạng thái hiện tại).
+ Chọn một trạng thái hàng xóm đầu tiên mà "tốt hơn" (theo một hàm đánh giá hoặc heuristic) so với trạng thái hiện tại và di chuyển đến đó.
+ Lặp lại quá trình này cho đến khi không tìm thấy hàng xóm nào tốt hơn trạng thái hiện tại (đạt đến "đỉnh") hoặc tìm thấy trạng thái đích.

Thuật toán có thể bị "kẹt" ở các đỉnh cục bộ những trạng thái mà không có hàng xóm nào tốt hơn, nhưng bản thân nó không phải là trạng thái đích. Nó cũng có thể bị kẹt trên "cao nguyên" nơi các hàng xóm có cùng giá trị heuristic. Vì nó chỉ đưa ra quyết định dựa trên cải thiện cục bộ và chọn hàng xóm tốt hơn đầu tiên mà không xem xét toàn bộ không gian, nó không đảm bảo tìm ra lời giải tối ưu.

                            SIMPLE_HC
![SIMPLEHC](https://github.com/Shiro74-coder/TTNT/blob/main/SimpleHC.gif)
# 2.3.2. Steepest Hill Climbing
Steepest Ascent Hill Climbing là một biến thể của thuật toán tìm kiếm cục bộ Hill Climbing. Điểm khác biệt chính so với Simple Hill Climbing là thay vì chọn hàng xóm "tốt hơn" đầu tiên mà nó tìm thấy, Steepest Ascent Hill Climbing sẽ đánh giá tất cả các hàng xóm và chọn ra hàng xóm "tốt nhất" (tức là hàng xóm có giá trị heuristic cải thiện nhiều nhất so với trạng thái hiện tại).

+ Bắt đầu từ một trạng thái ban đầu.
+ Ở mỗi bước, tạo ra và đánh giá tất cả các trạng thái "hàng xóm".
+ Nếu có ít nhất một hàng xóm tốt hơn trạng thái hiện tại, di chuyển đến hàng xóm tốt nhất (dốc nhất).
+ Lặp lại quá trình này cho đến khi không tìm thấy hàng xóm nào tốt hơn trạng thái hiện tại (đạt đến "đỉnh") hoặc tìm thấy trạng thái đích.

Tương tự như Simple Hill Climbing, nó vẫn có thể bị "kẹt" ở các đỉnh cục bộ hoặc cao nguyên. Quyết định dựa trên cải thiện cục bộ tốt nhất nên không đảm bảo lời giải toàn cục tối ưu.

                            STEEPEST_HC
![STEEPEST_HC](https://github.com/Shiro74-coder/TTNT/blob/main/SteepestHC.gif)
# 2.3.3. Stochastic Hill Climbing
Stochastic Hill Climbing là một biến thể của thuật toán tìm kiếm cục bộ Hill Climbing. Nó giới thiệu một yếu tố ngẫu nhiên vào việc chọn bước đi tiếp theo, nhằm mục đích có thể thoát khỏi các đỉnh cục bộ mà các phiên bản Hill Climbing đơn giản (Simple hoặc Steepest Ascent) dễ bị mắc kẹt.

+ Bắt đầu từ một trạng thái ban đầu.
+ Ở mỗi bước, tạo ra và đánh giá các trạng thái "hàng xóm".
+ Thay vì luôn chọn hàng xóm tốt nhất (Steepest Ascent) hoặc hàng xóm tốt hơn đầu tiên (Simple), Stochastic Hill Climbing chọn một hàng xóm "tốt hơn" một cách ngẫu nhiên. Xác suất chọn một hàng xóm tốt hơn có thể phụ thuộc vào mức độ cải thiện mà nó mang lại.
+ Nếu không có hàng xóm nào tốt hơn, thuật toán có thể dừng lại hoặc có thể cho phép di chuyển đến một trạng thái kém hơn với một xác suất nhất định ở một mức độ nào đó

Vẫn có khả năng bị kẹt ở đỉnh cục bộ, mặc dù yếu tố ngẫu nhiên có thể giúp nó khám phá không gian trạng thái rộng hơn một chút so với các phiên bản Hill Climbing đơn giản. Quyết định ngẫu nhiên và dựa trên cải thiện cục bộ không đảm bảo lời giải toàn cục tối ưu.

                            STOCHASTIC_HC
![Stochastic](https://github.com/Shiro74-coder/TTNT/blob/main/Stochastic.gif)
# 2.3.4. Simulated Annealing
Simulated Annealing là một thuật toán tối ưu hóa xác suất lấy cảm hứng từ quá trình luyện kim trong vật lý, nơi một kim loại được nung nóng rồi làm nguội từ từ để đạt được trạng thái cấu trúc tinh thể bền vững (năng lượng thấp). Trong tìm kiếm, SA được sử dụng để tìm kiếm một lời giải "đủ tốt" cho một bài toán tối ưu hóa, đặc biệt hữu ích để thoát khỏi các cực trị cục bộ mà các thuật toán leo đồi (Hill Climbing) thường mắc phải.
+ Trạng thái hiện tại và hàng xóm: Thuật toán bắt đầu với một trạng thái hiện tại và ở mỗi bước, nó xem xét một trạng thái "hàng xóm" được chọn ngẫu nhiên.
+ Hàm năng lượng : Tương tự như hàm heuristic trong các thuật toán tìm kiếm cục bộ khác, SA sử dụng một hàm để đánh giá "chất lượng" hoặc "năng lượng" của một trạng thái. Mục tiêu thường là tìm trạng thái có năng lượng thấp nhất
+ Chấp nhận nước đi:
+    Nếu trạng thái hàng xóm tốt hơn (năng lượng thấp hơn) trạng thái hiện tại, thuật toán luôn di chuyển đến trạng thái hàng xóm đó.
+    Nếu trạng thái hàng xóm tệ hơn (năng lượng cao hơn), thuật toán vẫn có thể di chuyển đến đó với một xác suất nhất định. Xác suất này phụ thuộc vào hai yếu tố: Mức độ "tệ hơn" của nước đi (DeltaE – sự chênh lệch năng lượng). Một tham số gọi là "nhiệt độ(T).
+ Lịch trình làm nguội: "Nhiệt độ" T ban đầu được đặt ở mức cao, cho phép thuật toán thường xuyên chấp nhận cả những nước đi tệ hơn (tăng tính khám phá). Sau đó, T giảm dần theo một "lịch trình làm nguội". Khi T giảm, xác suất chấp nhận nước đi tệ hơn cũng giảm theo, khiến thuật toán dần dần "ổn định" và tập trung vào việc khai thác các vùng tốt.

Xác suất chấp nhận một nước đi tệ hơn thường được tính bằng công thức: P = e^(−DeltaE/T)
Nếu lịch trình làm nguội đủ chậm và T_final đủ thấp, SA có xác suất cao tiến đến trạng thái tối ưu toàn cục. Tuy nhiên, trong thực tế với thời gian hữu hạn, nó không đảm bảo tìm thấy lời giải ngay cả khi có. Không đảm bảo tìm ra lời giải tối ưu toàn cục, nhưng thường tìm được lời giải "khá tốt" và có khả năng thoát khỏi các cực trị cục bộ tốt hơn Hill Climbing.

                            SIMULATED ANNEALING
![Simulated_Annealing](https://github.com/Shiro74-coder/TTNT/blob/main/Simulated_Annealing.gif)
# 2.3.5. Genetic 
Giải thuật Di truyền (GA) là một thuật toán tìm kiếm và tối ưu hóa lấy cảm hứng từ quá trình tiến hóa tự nhiên và chọn lọc tự nhiên. Nó hoạt động trên một quần thể các cá thể, mỗi cá thể đại diện cho một giải pháp tiềm năng cho bài toán. Qua các thế hệ, quần thể này được cải thiện dần thông qua các toán tử di truyền như chọn lọc, lai ghép, và đột biến.

+ Khởi tạo Quần thể: Tạo ra một tập hợp ban đầu các giải pháp ngẫu nhiên (hoặc gần ngẫu nhiên) cho bài toán.
+ Đánh giá Độ thích nghi : Mỗi cá thể trong quần thể được đánh giá bằng một hàm thích nghi (fitness function) để xác định "chất lượng" của nó (mức độ tốt của giải pháp mà nó đại diện).
+ Chọn lọc: Các cá thể "tốt hơn" có nhiều khả năng được chọn để tạo ra thế hệ tiếp theo.
+ Lai ghép: Các cặp cá thể "cha mẹ" được chọn sẽ trao đổi thông tin (gen) để tạo ra các cá thể "con" mới.
+ Đột biến: Một số thay đổi nhỏ, ngẫu nhiên được áp dụng cho các cá thể con để duy trì sự đa dạng trong quần thể và tránh hội tụ sớm về các giải pháp dưới tối ưu.
+ Lặp lại: Quá trình đánh giá, chọn lọc, lai ghép, và đột biến được lặp lại qua nhiều thế hệ, với hy vọng quần thể sẽ hội tụ về một hoặc nhiều giải pháp tối ưu hoặc gần tối ưu.

Không đảm bảo tìm thấy lời giải, đặc biệt là lời giải tối ưu, trong thời gian hữu hạn. Nó là một thuật toán tìm kiếm xác suất. Không đảm bảo tìm ra lời giải tối ưu. Chất lượng của giải pháp phụ thuộc vào nhiều yếu tố như kích thước quần thể, số thế hệ, các toán tử di truyền, và hàm thích nghi.

                            Genetic_GA
![Genetic_GA](https://github.com/Shiro74-coder/TTNT/blob/main/Genetic_GA.gif)
# 2.4. Các thuật toán tìm kiếm trong môi trường có ràng buộc
# 2.4.1. Backtracking
# 2.4.2. Generate and Test
# 2.4.3. AC-3
# 2.5. Các thuật toán tìm kiếm trong môi trường phức tạp
# 2.5.1. And Or Search
# 2.5.2. No Observable
# 2.5.3. Pratially Observable
# 2.6. Các thuật toán học tăng cường
# 2.6.1. Q-Learning
# 3. Kết luận






                          And_Or_Search
![And_Or_Search](https://github.com/Shiro74-coder/TTNT/blob/main/and_or_search.gif)

                          Search_no_Observation
![And_Or_Search](https://github.com/Shiro74-coder/TTNT/blob/main/search_no_obs.gif)
