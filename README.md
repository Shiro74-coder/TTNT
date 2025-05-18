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
# 2.1.5 Hình ảnh so sánh và nhận xét các thuật toán
Trạng thái 1:
Start State: "123456078"
Goal State: "123456780"

Trạng thái 2:
Start State: "123560478"
Goal State: "123456780"

Trạng thái 3:
Start State:  "142305786"
Goal State: "123456780"	

![image](https://github.com/user-attachments/assets/d2ef5cf4-f4d0-418b-9b0a-3c271111ff97)
![image](https://github.com/user-attachments/assets/37708a38-5846-4e48-a4fa-21dd7a651ff3)

Tính Tối ưu về Số Bước:
BFS, UCS, IDDFS: Cả ba thuật toán này đều tìm ra số bước di chuyển ít nhất (tối ưu) để đến trạng thái đích trong tất cả các trường hợp thử nghiệm. Điều này hoàn toàn phù hợp với lý thuyết, vì BFS và IDDFS đảm bảo tìm ra lời giải nông nhất, và UCS khi chi phí mỗi bước là 1 cũng hoạt động tương tự BFS.
DFS: Thuật toán DFS tìm ra đường đi với số bước lớn hơn đáng kể so với các thuật toán còn lại (ví dụ: 30 bước so với 2 ở Trạng thái 1; 48 bước so với 16 ở Trạng thái 3). Điều này cho thấy DFS không đảm bảo tính tối ưu về chiều dài đường đi; nó có xu hướng đi sâu vào một nhánh và có thể tìm thấy một lời giải dài hơn trước khi tìm ra lời giải ngắn nhất (hoặc không bao giờ tìm ra lời giải ngắn nhất nếu không duyệt hết).

Thời gian Thực thi:
BFS và UCS: Có thời gian thực thi khá tương đồng và tăng lên khi số bước của lời giải (độ khó của bài toán) tăng.
IDDFS: Thời gian thực thi của IDDFS cũng tăng theo độ khó của bài toán và thường cao hơn một chút so với BFS/UCS cho cùng một bài toán(ví dụ: 2.106s so với 1.653s cho Trạng thái 1; 10.825s so với 9.755s cho Trạng thái 3) . Điều này là do IDDFS lặp lại việc tìm kiếm ở các độ sâu nông hơn, mặc dù chi phí này thường không quá lớn so với việc tìm kiếm ở độ sâu cuối cùng.

DFS: Có thời gian thực thi cao nhất trong tất cả các trường hợp, và dường như không tương quan trực tiếp với độ sâu của lời giải tối ưu mà là độ sâu tối đa mà nó khám phá hoặc số lượng nút nó phải duyệt qua trong các nhánh dài. Ví dụ, ở Trạng thái 1 (2 bước tối ưu), DFS mất tới 18s để tìm ra một lời giải 30 bước. Điều này do việc triển khai DFS(có giới hạn độ sâu 50 và kiểm tra lặp trong path hiện tại) vẫn phải khám phá nhiều nhánh không hiệu quả.

Kết luận:
+ IDDFS nổi lên như một lựa chọn cân bằng tốt trong nhóm không thông tin: nó tìm ra lời giải tối ưu về số bước (giống BFS/UCS) và mặc dù thời gian có thể cao hơn BFS/UCS một chút, nhưng về mặt lý thuyết, nó có ưu điểm lớn về tiết kiệm bộ nhớ (điều này không thể hiện qua số liệu thời gian/số bước nhưng là một đặc tính quan trọng).
+ BFS và UCS hoạt động hiệu quả và tối ưu cho các bài toán có độ sâu lời giải không quá lớn. Tuy nhiên, chúng có thể gặp vấn đề về bộ nhớ và thời gian với các bài toán khó hơn nhiều.
+ DFS (với cách triển khai hiện tại) tỏ ra kém hiệu quả nhất cho bài toán tìm đường đi tối ưu trong 8-puzzle, cả về thời gian thực thi lẫn chất lượng lời giải (số bước). Nó có thể hữu ích trong các trường hợp không gian trạng thái rất lớn mà chỉ cần tìm bất kỳ lời giải nào và bộ nhớ là ưu tiên hàng đầu, nhưng với giới hạn độ sâu và cách nó tìm kiếm, nó không cạnh tranh được trong các trường hợp này.
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
# 2.2.5. Hình ảnh so sánh và nhận xét các thuật toán
Trạng thái 1:
Start State: "123456078"
Goal State: "123456780"

Trạng thái 2:
Start State: "123560478"
Goal State: "123456780"

Trạng thái 3:
Start State:  "142305786"
Goal State: "123456780"	

![image](https://github.com/user-attachments/assets/c435cf30-b48f-405c-96cc-69be1f21d465)
![image](https://github.com/user-attachments/assets/7b68cf9a-57c7-41cd-91c0-b875407eedfa)

Nhận xét: 
+ Tính tối ưu: A* và IDA* vượt trội trong việc đảm bảo tìm ra lộ trình ngắn nhất nhờ sự kết hợp giữa chi phí thực tế g(n) và chi phí ước tính h(n) (với heuristic chấp nhận được như Manhattan Distance).
+ Greedy chỉ dựa vào heuristic h(n), nên khi heuristic không "dẫn đường" tốt ở các trạng thái phức tạp, nó dễ bị lạc hướng và tìm ra đường đi dài, tốn thời gian. Beam Search cũng dựa vào heuristic để lựa chọn các ứng cử viên trong "chùm" nhưng có yếu tố giới hạn số lượng ứng cử viên được giữ lại.
+ Thời gian thực thi: Với các bài toán đơn giản, tất cả các thuật toán có thông tin đều nhanh. Khi độ khó tăng (Trạng thái 3), A* và IDA* thể hiện sự ổn định và hiệu quả hơn về thời gian so với Greedy.
Kết luận:
+ A* và IDA*: Lựa chọn hàng đầu để tìm đường đi ngắn nhất, hiệu suất tốt. IDA* thường ưu thế hơn về bộ nhớ.
+ Beam Search: Lựa chọn cân bằng, có thể nhanh nhưng hy sinh tính tối ưu hoàn toàn.
+ Greedy: Nhanh với bài dễ, nhưng không đáng tin cậy cho các bài toán phức tạp hoặc khi cần đảm bảo tối ưu.
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
# 2.3.6. Hình ảnh so sánh và nhận xét các thuật toán
Trạng thái 1:
Start State: "123456078"
Goal State: "123456780"

Trạng thái 2:
Start State: "123560478"
Goal State: "123456780"

Trạng thái 3:
Start State:  "142305786"
Goal State: "123456780"	

![image](https://github.com/user-attachments/assets/eeb7b3bd-ad78-4cd6-bdd4-9e061f2ddf09)
![image](https://github.com/user-attachments/assets/b1d04fb0-56b4-44da-9127-0560f1ca98f5)

Nhận xét:
Các biến thể Hill Climbing (Simple, Steepest Ascent, Stochastic):
+ Kết quả: Tìm được lời giải (thường là tối ưu hoặc gần tối ưu) cho các trạng thái dễ (Trạng thái 1 & 2). Tuy nhiên, tất cả đều bị kẹt và không tìm được lời giải cho trạng thái khó hơn (Trạng thái 3), minh họa rõ nhược điểm về cực trị cục bộ.
+ Hiệu suất: Thời gian chạy nhanh cho các bài dễ. Stochastic HC có thể cho số bước không tối ưu hơn Simple/Steepest HC một chút.

Simulated Annealing (SA):
+ Kết quả: Giải được trạng thái rất dễ (Trạng thái 1). Tuy nhiên, cũng bị kẹt ở các trạng thái khó hơn (Trạng thái 2 & 3), cho thấy các tham số mặc định có thể chưa tối ưu cho việc thoát khỏi cực trị cục bộ trong các trường hợp này.
+ Hiệu suất: Nhanh khi tìm được lời giải.

Genetic Algorithm (GA):
+ Kết quả: (Không có dữ liệu cho Trạng thái 1). Tìm được lời giải tối ưu cho Trạng thái 2. Quan trọng nhất, GA là thuật toán duy nhất trong nhóm này tìm được lời giải cho Trạng thái 3 (khó), dù lời giải có số bước lớn hơn (42 bước).
+ Hiệu suất: Thời gian chạy lâu hơn đáng kể, đặc biệt với bài toán khó, do xử lý cả quần thể. Chất lượng lời giải không đảm bảo tối ưu nhưng có khả năng tìm được lời giải khi các thuật toán khác thất bại.

Kết luận:
+ Hill Climbing (các biến thể): Nhanh cho bài dễ, dễ bị kẹt ở bài khó.
+ Simulated Annealing: Có tiềm năng thoát kẹt nhưng cần tinh chỉnh tham số; trong thử nghiệm này hoạt động chưa nổi bật ở bài khó.
+ Genetic Algorithm: Mạnh mẽ nhất trong việc tìm ra lời giải cho các trường hợp phức tạp (không bị kẹt), nhưng đánh đổi bằng thời gian và tính không tối ưu của lời giải.
# 2.4. Các thuật toán tìm kiếm trong môi trường có ràng buộc
# 2.4.1. Backtracking
Backtracking là một kỹ thuật giải thuật tổng quát, hoạt động bằng cách xây dựng giải pháp một cách từ từ, từng bước một. Tại mỗi bước, nếu việc lựa chọn một giá trị cho một biến (trong trường hợp này là một ô trên bảng puzzle) không vi phạm các ràng buộc đã định, thuật toán sẽ tiếp tục. Nếu tại một thời điểm nào đó, không thể tìm thấy giá trị hợp lệ cho biến tiếp theo, hoặc một lựa chọn dẫn đến vi phạm ràng buộc, thuật toán sẽ "quay lui" – tức là hủy bỏ lựa chọn trước đó và thử một lựa chọn khác. Quá trình này lặp lại cho đến khi tìm được một giải pháp hoàn chỉnh thỏa mãn tất cả các ràng buộc, hoặc đã thử hết mọi khả năng mà không tìm được giải pháp.
Để áp dụng Backtracking theo hướng CSP cho 8-puzzle, chúng em đã định nghĩa bài toán như sau:
+ Biến (Variables): Gồm 9 biến, mỗi biến tương ứng với một ô trên bảng 8-puzzle (ví dụ V0 đến V8).
+ Miền giá trị (Domains): Mỗi biến (ô) có thể nhận một giá trị trong tập từ 0 đến 8, trong đó số 0 đại diện cho ô trống.
+ Ràng buộc (Constraints): Ràng buộc chính và duy nhất trong trường hợp cơ bản này là AllDifferent. Nghĩa là, tất cả 9 ô trên bảng phải chứa các giá trị (số) khác nhau; không có hai ô nào được chứa cùng một số.

Backtracking có thể áp dụng cho nhiều loại CSP. Đảm bảo tìm ra giải pháp nếu có, vì nó duyệt một cách có hệ thống không gian tìm kiếm. Tuy nhiên rong trường hợp xấu nhất, nó có thể phải duyệt qua một số lượng rất lớn các khả năng. Thứ tự chọn biến và thứ tự thử giá trị có thể ảnh hưởng lớn đến hiệu suất.

                            Genetic_GA
![Genetic_GA](https://github.com/Shiro74-coder/TTNT/blob/main/Genetic_GA.gif)
# 2.4.2. Generate and Test
Sinh và Kiểm tra là một phương pháp tìm kiếm cơ bản và trực tiếp. Trong ngữ cảnh giải quyết Bài toán Thỏa mãn Ràng buộc (CSP), thuật toán này hoạt động theo hai bước chính lặp đi lặp lại:
+ Sinh (Generate): Tạo ra một ứng cử viên giải pháp hoàn chỉnh, tức là một phép gán đầy đủ giá trị cho tất cả các biến của bài toán.
+ Kiểm tra (Test): Kiểm tra xem ứng cử viên giải pháp vừa được sinh ra có thỏa mãn tất cả các ràng buộc của CSP hay không.

Nếu ứng cử viên thỏa mãn tất cả các ràng buộc, nó được coi là một lời giải. Nếu không, thuật toán sẽ loại bỏ ứng cử viên đó và quay lại bước "Sinh" để tạo ra một ứng cử viên mới. Quá trình này tiếp tục cho đến khi tìm được một lời giải hoặc đã đạt đến một giới hạn nào đó (ví dụ: số lần thử tối đa).
Để áp dụng phương pháp này cho bài toán 8-puzzle, Em đã định nghĩa lại bài toán theo cấu trúc của một CSP:
+ Biến (Variables): 9 ô trên bảng 8-puzzle (V0 đến V8).
+ Miền giá trị (Domains): Mỗi ô (biến) có thể nhận một giá trị từ tập {0, 1, 2, 3, 4, 5, 6, 7, 8}, với '0' đại diện cho ô trống.
+ Ràng buộc (Constraints): Ràng buộc cốt lõi là AllDifferent, tức là tất cả 9 ô phải chứa các giá trị (số) duy nhất, không có sự lặp lại.

Nếu được phép chạy đủ lâu (với max_attempts đủ lớn), về mặt lý thuyết, nó có thể tìm thấy trạng thái đích do tính ngẫu nhiên của việc sinh hoán vị sẽ bao phủ toàn bộ không gian các trạng thái hợp lệ (9! trạng thái). Không tối ưu về đường đi: Thuật toán này không tìm "đường đi" hay chuỗi hành động. Nó chỉ cố gắng "đoán mò" ra trạng thái đích. Do đó, không có khái niệm về tính tối ưu của đường đi ở đây. Hiệu suất rất thấp: Đây là nhược điểm lớn nhất. Với 8-puzzle có 9! = 362,880 trạng thái hợp lệ, việc tìm ra một trạng thái đích cụ thể bằng cách sinh ngẫu nhiên là rất không hiệu quả và có thể mất rất nhiều thời gian, hoặc không bao giờ tìm thấy trong một số lần thử hợp lý.

                            Genetic_GA
![Genetic_GA](https://github.com/Shiro74-coder/TTNT/blob/main/Genetic_GA.gif)
# 2.4.3. AC-3
AC-3 là một thuật toán được sử dụng để tiền xử lý hoặc trong quá trình giải các Bài toán Thỏa mãn Ràng buộc (CSPs). Mục tiêu chính của AC-3 là đạt được tính nhất quán cung.
+ Bài toán Thỏa mãn Ràng buộc (CSP): Được định nghĩa bởi một tập các biến, mỗi biến có một miền giá trị, và một tập các ràng buộc quy định các tổ hợp giá trị hợp lệ cho các tập con của biến.
+ Tính nhất quán cung: Một biến Xi được gọi là nhất quán cung với biến Xj nếu với mọi giá trị x trong miền của Xi, tồn tại một giá trị y trong miền của Xj sao cho (x,y) thỏa mãn ràng buộc giữa Xi và Xj. Và một CSP là nhất quán cung nếu mọi biến đều nhất quán cung với mọi biến khác.

AC-3 hoạt động bằng cách loại bỏ các giá trị không nhất quán khỏi miền giá trị của các biến, từ đó thu hẹp không gian tìm kiếm và giúp các thuật toán tìm kiếm (như Backtracking) hoạt động hiệu quả hơn.
Để áp dụng AC-3 như một CSP:
+ Biến: 9 ô trên bảng, V0,V1,...,V8 (trong mã nguồn là C0 đến C8). Mỗi biến đại diện cho giá trị số tại một ô.
+ Miền giá trị (Domains): Nếu một ô có giá trị đã biết (ví dụ, người dùng nhập '1', '5', '0'), miền của biến tương ứng chỉ chứa giá trị đó: Di={giá trị đã biết}. Nếu một ô chưa biết giá trị (ví dụ, người dùng nhập '?'), miền của biến tương ứng ban đầu chứa tất cả các giá trị có thể có: Di={0,1,2,3,4,5,6,7,8}.
+ Ràng buộc: Ràng buộc chính là AllDifferent: tất cả các biến (ô) phải có giá trị khác nhau. Điều này có nghĩa là với bất kỳ hai biến Vi và Vj (i khác j), giá trị của Vi phải khác giá trị của Vj.

Mục đích của AC-3 không trực tiếp tìm ra một giải pháp (một cấu hình puzzle hoàn chỉnh) nếu có nhiều khả năng. Thay vào đó, nó loại bỏ các giá trị rõ ràng là không thể khỏi miền của các biến, làm cho bài toán trở nên "đơn giản hơn".

                            Genetic_GA
![Genetic_GA](https://github.com/Shiro74-coder/TTNT/blob/main/Genetic_GA.gif)
# 2.5. Các thuật toán tìm kiếm trong môi trường phức tạp
# 2.5.1. And Or Search
Thuật toán AND-OR tìm kiếm trong cây AND-OR chứ không phải cây thông thường. Trong cây này:
+ Nút OR đại diện cho sự lựa chọn giữa các hành động.
+ Nút AND đại diện cho các trường hợp mà tất cả các nhánh con phải được giải quyết thành công (tức là các kết quả khả thi của một hành động không chắc chắn).

Bài toán 8-puzzle có các hành động xác định (mỗi nước đi chỉ dẫn đến một trạng thái kết quả duy nhất). 
+ Do đó, hàm RESULTS(state, action) trong EightPuzzleProblemAdapter luôn trả về một danh sách chỉ chứa một trạng thái.
+ Điều này làm đơn giản hóa logic của phương thức _and_search: nó chỉ cần xử lý một kết quả duy nhất này bằng cách gọi _or_search cho trạng thái đó.
+ Kết quả là, kế hoạch (plan) được tìm thấy là một chuỗi hành động tuần tự đơn giản, không phải là một kế hoạch có điều kiện phức tạp như trong trường hợp bất định.

Không đảm bảo tối ưu về độ dài đường đi: Đây là một đặc điểm quan trọng cần nhấn mạnh. Do thuật toán tìm và trả về giải pháp đầu tiên nó gặp phải theo kiểu duyệt sâu (DFS-like), giải pháp này không chắc chắn là đường đi ngắn nhất.

                            Genetic_GA
![Genetic_GA](https://github.com/Shiro74-coder/TTNT/blob/main/Genetic_GA.gif)
# 2.5.2. No Observable
No Observable Search là thuật toán tìm kiếm trong môi trường không quan sát được.
Môi trường không quan sát được bao gồm:
+ Trạng thái Niềm tin (Belief State): Thay vì biết một trạng thái hiện tại duy nhất, tác nhân duy trì một "trạng thái niềm tin" (belief state). Trạng thái niềm tin là một tập hợp tất cả các trạng thái vật lý mà tác nhân tin rằng mình có thể đang ở đó.
+ Hành động và Dự đoán: Khi tác nhân thực hiện một hành động, trạng thái niềm tin sẽ được cập nhật. Hành động được áp dụng cho mỗi trạng thái trong trạng thái niềm tin hiện tại. Trạng thái niềm tin mới sẽ là tập hợp tất cả các trạng thái kết quả có thể có. Quá trình này được gọi là dự đoán.
+ Mục tiêu: Tìm một chuỗi các hành động để đưa tác nhân từ một trạng thái niềm tin ban đầu đến một trạng thái niềm tin mà tất cả các trạng thái trong đó đều là trạng thái đích.

Cách Hoạt động:

+ Khởi đầu với Trạng thái niềm tin (Belief State): Thuật toán không làm việc với một trạng thái cụ thể duy nhất mà với một tập hợp các trạng thái có thể có, gọi là "trạng thái niềm tin" (belief state) ban đầu. Đây là tất cả những trạng thái mà tác nhân nghĩ rằng mình có thể đang ở đó. Mục tiêu cũng là một "tập hợp các trạng thái đích".
+ Tìm kiếm trên không gian các trạng thái niềm tin: Thuật toán thực hiện một tìm kiếm theo BFS để tìm một chuỗi các hành động (ví dụ: Lên, Xuống, Trái, Phải). Mỗi "nút" trong quá trình tìm kiếm này không phải là một trạng thái puzzle đơn lẻ, mà là một trạng thái niềm tin (một tập các trạng thái puzzle).
+ Khi một hành động được thử nghiệm trên một trạng thái niềm tin hiện tại: Hành động đó được áp dụng cho tất cả các trạng thái trong trạng thái niềm tin hiện tại. Tập hợp tất cả các trạng thái kết quả (sau khi loại bỏ trùng lặp) tạo thành trạng thái niềm tin mới.
+ Mục tiêu là tìm một chuỗi hành động sao cho khi áp dụng chuỗi đó, trạng thái niềm tin kết quả là một tập hợp mà mọi trạng thái trong đó đều là trạng thái đích.

Kết quả: Nếu thành công, thuật toán trả về chuỗi hành động tìm được. Giao diện sau đó sẽ mô phỏng việc áp dụng các hành động này và hiển thị sự thay đổi của trạng thái niềm tin.
Nhận xét: Không gian tìm kiếm là không gian của các tập hợp trạng thái (trạng thái niềm tin), lớn hơn nhiều so với không gian của các trạng thái vật lý đơn lẻ. Tương tự nếu được triển khai theo kiểu BFS, nó sẽ tìm thấy chuỗi hành động ngắn nhất nếu có lời giải. Chi phí có thể rất tốn kém vì kích thước của các trạng thái niềm tin có thể lớn và số lượng trạng thái niềm tin có thể rất nhiều.
# 2.5.3. Pratially Observable
Partially Observable Search là thuật toán tìm kiếm trong môi trường quan sát được một phần. Đây là một bước tiến bộ hơn so với môi trường không quan sát được, vì giờ đây tác nhân có thể nhận được một số thông tin từ môi trường sau mỗi hành động.
+ Trạng thái niềm tin: Tương tự như No Observable Search, tác nhân vẫn duy trì một trạng thái niềm tin, là một tập hợp các trạng thái vật lý mà nó tin rằng mình có thể đang ở đó.
+ Chu trình Hành động - Quan sát - Cập nhật:
+ Dự đoán: Tác nhân thực hiện một hành động. Trạng thái niềm tin hiện tại được cập nhật thành một trạng thái niềm tin mới bằng cách áp dụng hành động đó cho tất cả các trạng thái trong niềm tin hiện tại.
+ Quan sát: Sau khi hành động, tác nhân nhận được một quan sát từ môi trường.
+ Cập nhật: Trạng thái niềm tin dự đoán sau đó được "lọc" hoặc "cập nhật" dựa trên quan sát vừa nhận được. Chỉ những trạng thái trong niềm tin dự đoán mà nhất quán với quan sát đó mới được giữ lại. Điều này thường làm cho trạng thái niềm tin mới trở nên nhỏ hơn và chính xác hơn.

Mục tiêu: Tìm một chuỗi các hành động (có thể là một chính sách phụ thuộc vào quan sát) để đưa tác nhân từ trạng thái niềm tin ban đầu đến một trạng thái niềm tin mà tất cả các trạng thái trong đó đều là trạng thái đích.
Nhận xét: Do có sự kết hợp dự đoán và cập nhật giúp cho Pratially Observale Search tốt hơn No Observable Search. Tuy nhiên độ phức tạp vẫn rất cao do làm việc với không gian các trạng thái niềm tin. Việc cập nhật dựa trên quan sát giúp thu hẹp trạng thái niềm tin, có thể làm giảm sự bùng nổ ở một mức độ nào đó so với No Observable. Chuỗi hành động tìm được (nếu là chuỗi cố định) có thể không phải lúc nào cũng là tối ưu nhất trong mọi tình huống thực tế, vì nó được tìm kiếm dựa trên việc dự đoán trạng thái niềm tin mà không biết trước các quan sát sẽ nhận được. Các thuật toán phức tạp hơn có thể tìm ra các "chính sách" phân nhánh dựa trên các quan sát khác nhau.

# 2.6. Các thuật toán học tăng cường
# 2.6.1. Q-Learning
Q-learning là một thuật toán học tăng cường không cần mô hình (model-free), dựa trên giá trị (value-based). Mục tiêu của nó là học một chính sách tối ưu, cho biết hành động nào là tốt nhất để thực hiện tại mỗi trạng thái, nhằm tối đa hóa tổng phần thưởng tích lũy trong tương lai.
+ Q-learning học một hàm giá trị hành động, ký hiệu là Q(s,a), đại diện cho "chất lượng" (phần thưởng kỳ vọng trong tương lai) của việc thực hiện hành động a tại trạng thái s, và sau đó tuân theo chính sách tối ưu.
+ Giá trị Q được cập nhật lặp đi lặp lại thông qua kinh nghiệm mà tác nhân thu được khi tương tác với môi trường, sử dụng công thức cập nhật Bellman: Q(s,a)←Q(s,a)+α⋅[r+γ⋅maxa′Q(s′,a′)−Q(s,a)] Trong đó: 
+ α (alpha): Tốc độ học (learning rate).
+ r: Phần thưởng nhận được sau khi thực hiện hành động a tại trạng thái s và chuyển đến trạng thái s′.
+ γ (gamma): Hệ số chiết khấu (discount factor), quyết định tầm quan trọng của phần thưởng trong tương lai.
+ s′: Trạng thái tiếp theo.
+ maxa′Q(s′,a′): Giá trị Q lớn nhất có thể đạt được từ trạng thái s′.
+ Thăm dò (Exploration) và Khai thác (Exploitation): Để học được chính sách tốt, tác nhân cần cân bằng giữa việc thử các hành động mới để khám phá môi trường (thăm dò) và việc chọn các hành động mà nó đã biết là tốt (khai thác). Phương pháp phổ biến là epsilon-greedy: với xác suất ϵ (epsilon), chọn một hành động ngẫu nhiên; ngược lại (với xác suất 1−ϵ), chọn hành động có giá trị Q cao nhất. ϵ thường giảm dần theo thời gian.

Số lượt chơi thử/episodes để huấn luyện): 50000. Đây là số lần mà tác nhân sẽ thử chơi từ trạng thái bắt đầu cho đến khi đạt được trạng thái đích hoặc đạt đến số bước tối đa trong một lượt chơi.

Tốc độ học(alpha): 0.1. Dùng để xác định mức độ mà thông tin mới (từ phần thưởng và giá trị Q tương lai) sẽ ghi đè lên thông tin cũ trong bảng Q.

Hệ số chiết khấu(gamma): 0.95. Quyết định tầm quan trọng của phần thưởng trong tương lai. Giá trị gần 1 làm cho tác nhân quan tâm nhiều hơn đến phần thưởng dài hạn.

epsilon: Khởi tạo là 1.0. Ban đầu, epsilon=1.0 có nghĩa là tác nhân sẽ luôn chọn hành động một cách ngẫu nhiên (ưu tiên thăm dò).

Tốc độ giảm (epsilon): 0.99995. Sau mỗi bước epsilon sẽ được nhân với giá trị này, làm cho nó giảm dần

Giá trị epsilon tối thiểu: 0.05. Đảm bảo rằng ngay cả khi đã huấn luyện nhiều, tác nhân vẫn có một xác suất nhỏ (ở đây là 5%) để thực hiện hành động ngẫu nhiên, giúp tránh bị kẹt hoàn toàn vào một chính sách dưới tối ưu.

Số bước tối đa trong một episode: 1000. Giới hạn số hành động mà tác nhân có thể thực hiện trong một lượt chơi thử. Nếu không đạt được đích sau số bước này, episode đó sẽ kết thúc.

Có khả năng hội tụ đến đường đi ngắn nhất nếu huấn luyện đủ lâu và các tham số phù hợp. Tuy nhiên Thời gian huấn luyện lâu, cần rất nhiều lượt thử để học hiệu quả, đặc biệt với không gian trạng thái lớn của 8-puzzle, tốn bộ nhớ (Q-table): Lưu trữ giá trị Q cho mọi cặp (trạng thái, hành động) có thể rất lớn (9! trạng thái). Hiệu quả phụ thuộc lớn vào việc chọn đúng tốc độ học, hệ số chiết khấu, và chiến lược epsilon.

# 3. Kết luận






                          And_Or_Search
![And_Or_Search](https://github.com/Shiro74-coder/TTNT/blob/main/and_or_search.gif)

                          Search_no_Observation
![And_Or_Search](https://github.com/Shiro74-coder/TTNT/blob/main/search_no_obs.gif)
