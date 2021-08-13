---
layout: post
title: "[Dịch] Lược sử về GIMP"
date: 2021-08-12 22:00:00+0700
description: Tóm tắt về quá trình phát triển của GIMP cho đến thời điểm phát hành phiên bản 1.0
comments: true
---
*Bài viết này được dịch từ bài [A Brief (and Ancient) History of GIMP](https://www.gimp.org/about/ancient_history.html){:target="_blank"} trên trang web của GIMP.*

Mục lục 
1. 
{:toc}

>Editor’s note: This history was written around the release of GIMP 1.0 in 1998 and has actually become a historical document all on its own. Some of the dates are not accurate (due to internet technology limitation (Google hadn’t indexed Usenet yet). Yet still a good document with many of the details perfectly intact.	

Dịch

>Ghi chú của biên tập viên: Bản ghi chép này được viết vào thời điểm phát hành GIMP 1.0 vào năm 1998 và thực sự đã trở thành một tài liệu lịch sử. Một số ngày tháng không chính xác do giới hạn công nghệ internet (Google chưa lập chỉ mục Usenet). Tuy nhiên, đây vẫn là một tài liệu tốt với nhiều chi tiết hoàn toàn nguyên vẹn. 

Với tất cả các cuộc thảo luận và lý thuyết đang diễn ra về các mô hình phát triển Phần mềm Tự do, tôi nghĩ rằng đây là thời điểm phù hợp đề đưa ra một ví dụ cụ thể. Tôi đã cố gắng trình bày một cách chính xác nhất và hy vọng kinh nghiệm của tôi khi làm việc trong nhóm này có thể mang lại lợi ích cho các dự án khác.

Giống như việc phát triển GIMP hiện tại, tôi không thực hiện bài viết này một mình. Bài viết này là tổng hợp kiến ​​thức từ rất nhiều người trên #gimp, một số điều thậm chí đã tồn tại từ trước trước khi tôi bắt đầu. Bản sử này sẽ không thể thành hiện thực nếu không có sự giúp đỡ của josh, Raph, Adrian, Xach, yosh và tất cả mọi người trên #gimp. Dù không được tôi kể tên ở đây nhưng rất nhiều trang và nhiều người đã và đang đóng góp vào sự thành công của GIMP. Bạn có thể truy cập [http://www.gimp.org](http://www.gimp.org){:target="_blank"} để xem danh sách đầy đủ hơn.

-- Seth Burgess

## Buổi ban đầu

H	ai chàng sinh viên tại Berkeley, Spencer Kimball và Peter Mattis, quyết định viết một chương trình xử lí hình ảnh thay vì viết một trình biên dịch bằng Scheme/lisp trong lớp của giáo sư Fateman (CS164). Không ai trong nhóm có kinh nghiệm về đồ họa vi tính, nhưng nó có vẻ như là một dự án hấp dẫn. Họ cũng được giáo sư Forsythe khuyến khích phát triển một số tính năng mới cho phần mềm - có tin đồn rằng chức năng cắt thông mình (intelligent scissors) là dự án Spencer thực hiện trong lớp CS280. Vì vậy, Spencer và Peter tạo ra **General Image Manipulation Program**, gọi tắt là **GIMP** . Họ đã phát triển nó trong một thời gian khá dài trước khi công khai nó - có thể là khoảng 9-10 tháng. Đến lần phát hành công khai đầu tiên, họ đã có một sản phẩm hoạt động được.

GIMP có rất nhiều thứ đi kèm trong bản phát hành công khai đầu tiên, phiên bản 0.54 (tháng 1 năm 1996). Có thể kể đến trong đó là hệ thống plug-in, hệ thống này cho phép các nhà phát triển tạo thêm các chức năng bên cạnh những gì đã có trong bản phân phối chính. Bên cạnh đó, GIMP có một số công cụ cơ bản để vẽ và làm việc với kênh màu. GIMP còn có một tính năng độc nhất vô nhị ở thời điểm đó là tính năng hoàn tác. GIMP đã có những người dùng trung thành. GIMP đã được bảo vệ bởi giấy phép GPL. Và GIMP  cũng có một cái tên tuyệt vời.

Nhưng không phải mọi thứ đều suôn sẻ với GIMP. Nó xảy ra sự cố khá thường xuyên, có thể do plug-in hoặc các vấn đề trong mã nguồn chính gây ra. GIMP được phát triển dựa trên bộ công cụ GUI của Motif, điều này đã hạn chế số lượng lượng người sử dụng. Đồng thời, hạn chế này khiến cho việc phát triển plug-in khó khăn hơn, nhiều ý tưởng hay đã không thể thực hiện được. Một vài người thậm chí cứ thế mà tuyên bố rằng GIMP ổn định hơn Photoshop mặc cho những điều kể trên vẫn xảy ra.

Vì vậy, giống như rất nhiều dự án, từ một khởi đầu khá khiêm tốn  GIMP đã trở thành một dự án thu hút được nhiều sự ủng hộ từ cộng đồng. Ban đầu nó hai nhà phát triển chỉ âm thầm làm việc. Không có quảng bá hay một kế hoạch hoành tráng nào, Spencer và Peter đơn giản là phát triển một phần mềm cho một mục đích cụ thể. GIMP không hoàn hảo, nhưng đó là một thành quả đáng kinh ngạc của hai lập trình viên còn là sinh viên, phát triển phần mềm độc lập và không có sự hỗ trợ nào từ bên ngoài.

## Thêm nhiều người dùng

Một trong những bước đầu tiên sau bản phát hành 0.54 là tạo danh sách gửi thư cho các nhà phát triển. Chắc hẳn Peter và Spencer muốn có phản hồi về chương trình mới và danh sách gửi thư (mailling list) là một cách thuận tiện để thực hiện việc này. Đó cũng là một cách dễ dàng và hiệu quả để thông báo cho cho mọi người về những gì đang diễn ra trong quá trình phát triển sản phẩm. Cho dù lý do là gì, danh sách gửi thư đầu tiên đã tạo ra được kênh liên lạc để những người có cùng sở thích trao đổi về dự án.

Hòm thư cứ thế nhiều lên, nhưng đôi khi có những câu hỏi không phù hợp. Các nhà phát triển có thể giỏi về con trỏ và cấu trúc dữ liệu nhưng lại không thể giải thích cho bạn hiểu cách sử dụng công cụ xử lí ảnh một cách hiệu quả. Chính vì thế, vào ngày 5 tháng 7 năm 1996, danh sách bàn đầu gimp-list được chia thành gimp-user và gimp-developer dành cho người dùng và cho các nhà phát triển.

Ngay sau khi GIMP đến với cộng đồng, các trang web về GIMP bắt đầu xuất hiện. Tất nhiên phải kể đến trang web chính thức của GIMP đặt tại Berkeley, nhưng mà các phần mềm khác không có là những trang do người dùng lập nên để hướng dẫn nhau sử dụng phần mềm.

Người dùng GIMP, chẳng hạn như Zach Beane (Xach), bắt đầu tạo các bài hướng dẫn cho GIMP. Trang của Zach, trong một thời gian, các bài hướng dẫn mới được đăng tải lên mỗi ngày. Những người khác cũng làm tương tự, họ khoe các tác phẩm được và trình diễn các kĩ thuật với GIMP. Nếu bạn muốn bắt đầu với GIMP, các trang web này sẽ rất phù hợp để giúp bạn làm quen.

Federico Mena Quintero, hay thường được biết đến với tên gọi Quartic, là tác giả của một trang tổng hợp các tài nguyên về GIMP. Do đó, trang của anh ấy nhanh chóng trở thành đầu mối cho các thông báo về plug-in mới và giới thiệu các tác phẩm đẹp mắt. Anh ấy cũng đưa lên đó các plug-in do chính anh phát triển.

Larry Ewing đã góp phẩn phổ biến GIMP bằng cách tạo ra nhân vật Linux Penguin nổi tiếng hiện nay (mà một số người gọi là Tux), bằng GIMP 0.54. Cụ thể, anh ấy tạo ra một trang web để chia sẻ về quá trình thực hiện tác phẩm trên. Đây có lẽ là lần đầu tiên danh tiếng của GIMP đến được với nhiều người như vậy.

## Bộ công cụ mới - Dòng phiên bản 0.60:

Peter đã thực sự phát ngán với Motif. Vì vậy, anh quyết định viết bộ công cụ của riêng mình. Anh ấy gọi chúng là gtk và gdk, viết tắt của Gimp Tool Kit (Bộ công cụ Gimp) và Gimp Drawing Kit (Bộ công cụ vẽ Gimp). Peter nói với chúng tôi rằng lúc bấy giờ họ chưa bao giờ có ý định để nó trở thành một bộ công cụ phổ biến - họ chỉ muốn một thứ hữu ích để sử dụng với GIMP và đó “có vẻ như là một ý tưởng hay vào thời điểm đó”. Sau đó, tên của phàn mềm được thay đổi; General Image Manipulation Program được đổi thành GNU Image Manipulation Program.

Lức này, dòng sản phẩm 0.6x vẫn đang được thử nghiệm và chưa thực sự hoàn thiện. Các plug-in không tương thích với phần lớn các plug-in được phát triển cho phiên bản 0.54. Các tác giả chưa thể cập nhật kịp thời các plug-in của họ để sử dụng trong phiên bản mới. Không chỉ vậy, mọi người không muốn viết tài liệu cho dòng sản phẩm 0.6x, các tính năng còn chưa hoàn thiện và không tương thích với nhau.

Nói chung, dòng sản phẩm 0.6x trở nên khó sử dụng hơn so với phiên bản 0,54 tiền nhiệm. Các sự cố xảy ra ngẫu nhiên hơn và thường xuyên hơn. Chỉ những người thực sự mong muốn dự án phát triển dự án mới tải về các phiên bản 0.6x. Do đó người dùng không mặn mà với việc sử dụng phiên bản mới. Cho dù nhiều kế hoạch phát triển chức năng mới được công bố trên trang web của Berkeley, điều đó không thể lấy được cảm tình của người dùng khi chính bản thân chương trình không thể đáp ứng được yêu cầu của người dùng. Họ thà sử dụng phiên bản cũ vẫn hoạt động tốt và viết plug-in cho nó còn hơn sử dụng phiên bản mới không ổn định.

Các phiên bản của dòng 0.60 là cơ hội để nhà phát triển tạo tạo thêm các chức năng. Nếu nó được cài đặt, và nó hoạt động, tình thế có thể được cứu vãn. Trước khi quá muộn, các nhà phát triển đã thực hiện một nỗ lực kịp thời để ổn định lại phần mềm, tuy nhiên việc thêm các chức năng hay ho vẫn là mục tiêu được ưu tiên hàng đầu. Điều này có thể được gói gọn trong lời của Andreas Dilger:

>"It’s good to see that the next version of GIMP is here.
Let the enhancing begin!"

Dịch:

>"Phiên bản tiếp theo của GIMP cần được hoàn thiện. Nào, bắt tay vào cải thiện nó thôi"

## Phiên bản 0.99 - Hành trình dài đến với 1.0

Vào ngày 26 tháng 2 năm 1997, Spencer và Peter (S&P) đã phát hành phiên bản 0.99. Các mục tiêu chính là chỉnh sửa các plug-in để tương thích với hệ thống bộ nhớ và API mới, điều này đã không được quan tâm nhiều trên các phiên bản 0.6x. Một phiên bản mới của gtk/gdk cũng được ra đời với tên gọi GTK+. Phiên bản này đã được cải tiến đáng kể so với phiên bản tiền nhiệm.

Các bản phát hành lần lượt được tung ra cho đến 0,99,9, với tốc độ không ngờ. Từ phiên bản 0.99.9 các phiên bản được phát hành thưa hơn trước. Trong khoảng thời gian đó, Trent Jarvi đã tổng hợp các cập nhật nhỏ đang nổi xung của phiên bản 0.99.9 và phát hành chúng khá thường xuyên. Cuối cùng, S&P đã thực hiện phát hành GTK+ phiên bản mới và GIMP 0.99.10 vào ngày 9 tháng 6 năm 1997. Đây cũng là bản phát hành cuối cùng của họ.

S&P đã tốt nghiệp đại học, đã có công việc ổn định và không còn thời gian để thực hiện dự án nữa. Không có người kế nhiệm nào được S&P chỉ định, và họ cũng giấu mọi người về dự định rời đi.

## Những bản phát hành sớm

Spencer và Peter giờ đã rời đi mà không nói lời tạm biệt, nhưng điều này không ngăn cản được những người dùng nhiệt thành; một số bản phát hành sớm không chính thức đã được thực hiện trong khi Spencer hoặc Peter vấn im hơi lặng tiếng. Việc theo dõi các bản vá, các bản phát hành trước đã trở thành một vấn đề nan giải. May mắn thay, Matt Hawkins là người đứng ra nhận xử lý chúng, và giúp những con người phàm tục chúng ta duy trì phần mềm cho đến khi ai đó trở lại sân khấu trung tâm.

Federico Mena Quintero (Quartic) đã chỉ đạo các bản phát hành trong một thời gian. Dưới sự hướng dẫn của anh, phong trào hướng tới sự xây dựng phần mềm ổn định và có thể sử dụng. Vào ngày phát hành phiên bản 0.99.14, Quartic đã thông báo đóng băng tính năng - không có tính năng mới nào được thêm vào cho đến 1.0. Các tính năng thú vị, một số trong đó được triển khai, đã được tạm gác sang một bên để hướng tới một bản phát hành ổn định.

Quartic vẫn duy trì hoạt động của GIMP cho đến khi anh ta phải tập trung vào các dự án (có liên quan) khác. Tuy nhiên, không có khoảng nghỉ nghiêm trọng nào xảy ra giữa giai đoạn của Quartic và giai đoạn kế cận.

## Phương thức giao tiếp mới

Danh sách gửi thư rất tốt, khi chúng hoạt động trơn tru. Và các trang web là công cụ tuyệt vời để giới thiệu các mẹo và trình bày dữ liệu. Nhưng chúng không thể hiệu quả bằng các cuộc trao đổi thời gian thực, nơi mọi người cùng trao đổi và cùng suy nghĩ, đồng thời nó giúp cho giai đoạn tìm và gỡ lỗi dễ dàng hơn. Để thực hiện điều này, GIMP đã tạo kênh irc của riêng mình, #gimp. #gimp ra đời vào khoảng gần tháng 2 năm 1997.

Công bằng mà nói, #gimp không phải lúc nào cũng được dùng để xử lý lỗi hoặc bàn bạc các kế hoạch GIMP trong tương lai. Nhưng nhìn chung, nó trở thành nơi hỗ trợ kỹ thuật rất hữu ích cho người dùng GIMP và là nơi để các nhà phát triển có thể khích lệ và giúp đỡ lẫn nhau. Một vài tuần trước, khi tôi hỏi rằng liệu GIMP sẽ đi về đâu nếu không có #gimp, tôi đã nhận được câu trả lời từ 'chắc là không đến đâu cả' đến 'hoàn toàn không là gì'. Nó cho phép mọi người nói về những gì thực sự cần thiết và những hoạt động nào họ có thể tham gia sẽ thực sự giúp ích cho dự án.

## Một mô hình phát triển mới

Với sự ra đi của các nhà lãnh đạo dự án Spencer và Peter, và bây giờ là Quartic, và GIMP hiện chia thành hai phần: phát triển bộ công cụ và phát triển chương trình, đã đến lúc phải có những người lãnh đạo mới. Phải không nào? Đó chính xác là những gì mô hình bazaar sẽ thực hiện. Tuy nhiên, như với bất kỳ mô hình nào, có những tình huống không thể lường trước được.

Trong hệ thống mới, có các thành viên trong nhóm được chỉ định; Ví dụ, Manish Singh (yosh) phụ trách phát hành. Adrian Likins, duy trì dữ liệu. Larry Ewing (lewing), Matthew Wilson (msw) và một số người khác sửa lỗi và làm những thứ rắc rối khác. Cũng có nhiều sự chồng chéo giữa cộng đồng nhà phát triển của GIMP và các dự án liên quan khác. Nhưng họ làm việc như một nhóm - không ai là trưởng dự án. Mỗi người đều có những đóng góp của riêng mình và tất cả chúng ta đều biết nên tham khảo ai khi chúng ta không biết cách làm điều gì đó hoặc muốn có lời khuyên hoặc lựa chọn. Các quyết định quan trọng liên quan đến số phận của GIMP chủ yếu được quyết định trên #gimp, thông qua nỗ lực của nhóm này.

## Sự khác biệt

Trong năm vừa qua, một số trang web đã mọc lên với các mục đích khác nhau, với đích đến chung là hỗ trợ người dùng và nhà phát triển GIMP.

Vào ngày 13 tháng 4 năm 1997, [http://xach.dorknet.com/gimp/news/](http://xach.dorknet.com/gimp/news/)]{:target="_blank"}, GIMP News ra đời. Zach là người có công lớn nhất trong hoạt động này. Trang web này cung cấp thông tin được cập nhật hàng ngày về quá trình phát triển GIMP. Nếu bạn tạo một plug-in, Zach biết đến nó và sẽ thông báo với cả thế giới về nó. Nếu một bản phát hành mới được thực hiện, thông tin qua trang web sẽ đến tay người dùng nhanh hơn so với danh sách gửi thư. Các hướng dẫn của anh ấy và trang báo cáo lỗi (được thêm sau đó) cũng được đăng tải trên trang web tin tức.

Đồng thời, chúng tôi cũng nhận được sự trợ giúp rất lớn trong việc theo dõi số lượng khổng lồ các plug-in và các ý tưởng plug-in. GIMP Plug-in Registry (Sổ đăng ký plug-in GIMP) cho phép tác giả cập nhật plug-in của họ và mọi người đăng ký kế hoạch của họ cho các plug-in trong tương lai. Nếu bạn là tác giả của plug-in, bạn đăng ký nó tại đây; nó sẽ được cập nhật liên tục, và người dùng có thể lựa chọn và tải xuống các plug-in mới nhất. Thậm chí bạn có lên 'danh sách mua sắm' tổng hợp lại những thứ bạn muốn và tải chúng về một lần.

Vào cuối tháng 5 năm 1997, tôi bắt đầu với GIMP Bugs. Công việc chính của tôi là tổng hợp lỗi từ danh sách của nhà phát triển cho các cuộc thảo luận sắp tới và sắp xếp chúng thành một biểu đồ dễ đọc để các nhà phát triển xem xét. Tôi thực hiện việc này "bằng cơm", nhưng chỉ cần một hoặc hai báo cáo lỗi mỗi ngày, 
cũng không khó khăn lắm vì tôi có thể dùng câu lệnh Perl để xử lí. Tôi xếp các lỗi theo mức độ ưu tiên, để các nhà phát triển với chuyên môn và cấp độ khác nhau có thể tập trung vào các lỗi khác nhau. Tôi cũng cẩn thận kiểm tra và tái tạo từng lỗi bằng GIMP mình và làm rõ nó trong báo cáo. Nó đã trở thành danh sách việc phải làm và được cập nhật thường xuyên.

Một khía cạnh thường bị bỏ qua và đánh giá thấp của một dự án lớn là tài liệu. Chúng tôi đã xây các hướng dẫn nhỏ, dần dần cho đến khi chúng tôi nhận được một cái gì đó tốt hơn nhiều, khá bất ngờ. Vào ngày 7 tháng 10 năm 1997, hai người dùng, Karin Kylander và Olof S., đã công bố [http://www.dtek.chalmers.se/~d95olofs/manual/gimpmana.html](http://www.dtek.chalmers.se/~d95olofs/manual/gimpmana.html){:target="_blank" } Hướng dẫn sử dụng Gimp (GIMP User Manual - GUM).

Bây giờ nó là một danh sách toàn diện của từng chức năng trong GIMP. Tài liệu đồ độ với hơn 200 trang này đại diện cho một lượng lớn công việc và là tài sản vô giá cho bất kỳ ai đang tìm hiểu một phần mềm. Những người dùng này đã trở thành chuyên gia thực sự với các công cụ, có thể tốt hơn bất kỳ nhà phát triển nào. Họ thu thập kiến ​​thức từ bất kỳ ai họ có thể. Sau đó, họ chọn chia sẻ kiến ​​thức đó với thế giới. Nên nhớ rằng phần lớn công việc được họ thực hiện, trước khi có bất kỳ sự trợ giúp nào từ bên ngoài hay thậm chí chưa ai biết đến sự tồn tại của nó. **Cập nhật:** Hiện nay GUM đến hơn 600 trang!

## Một mô hình phát hành khác

Bởi vì các nhà phát triển là những người thiếu kiên nhẫn, họ không muốn đợi cho đến khi có bản phát hành tiếp theo để mày mò thay đổi mã nguồn. CVS là giải pháp mà GIMP sử dụng cho vấn đề này. Hệ thống tạo phiên bản này cho phép người dùng cũng như các nhà phát triển tải xuống GIMP mới nhất và các nhà phát triển thực hiện các thay đổi. Hơn nữa, nó cho phép dễ dàng loại bỏ các thay đổi - mọi thay đổi đều được ghi lại và có thể được đảo ngược. Mặc dù có một số sự cố máy chủ với CVS, nó đã giúp phát hiện ra một số lỗi trước khi phát hành phiên bản Beta. Dù sao thì nó cũng tốt hơn việc xử lý vô số bản vá bằng tay.

## Tham gia thương mại

Trái ngược với hầu hết các dự án phần mềm miễn phí, GIMP có tham gia vào thương mại. Một số nhà phát triển GIMP (và có thể cả những người khác) đã nhìn thấy cơ hội kiếm tiền từ việc bán các bản phái sinh và các plug-in. Họ cũng muốn bán CD-ROM của phiên bản 1.0 của GIMP, đi kèm với đó là các sản phẩm và phần mềm liên quan.

Cuối cùng, [http://www.wilberworks.com](http://www.wilberworks.com){:target="_blank"} WilberWorks được thành lập. Một số nhà phát triển GIMP và “cộng tác viên” nhận thu nhập nho nhỏ từ công việc của họ trong dự án, làm việc theo hình thức khoán, cũng đủ để uống cà phê nhưng không nhiều. 

Trái với suy nghĩ của nhiều người, điều này hoàn toàn không ảnh hưởng đến sự phát triển của GIMP. Tất cả công việc được thực hiện trên GIMP vẫn là GPL. Tiền không phải là động lực chính cho công việc. Nó chỉ đơn giản là một đóng góp đó nho nhỏ mà WilberWorks rất biết ơn.

WilberWorks đã đưa tôi ra khỏi công việc theo dõi lỗi - họ đã thiết lập một hệ thống theo dõi lỗi vượt trội trên máy chủ của họ. 'Nhân viên' của WilberWorks có thể đăng nhập vào trang web và phản hồi các lỗi. Nhiều báo cáo có thể được sửa đổi đồng thời trong cơ sở dữ liệu. Các lỗi không bị bỏ quên trên hệ thống này - sau khi được xử lí, chúng vẫn được lưu lại thông tin. Người dùng có thể (mặc dù hiếm khi làm điều đó) đăng nhập với tư cách khách và duyệt qua các báo cáo và câu trả lời trước đó.

Hiện tại, chính sách của WilberWorks là trả lời tất cả các báo cáo lỗi, miễn là chúng phải là thư rác hoặc địa chỉ email không hợp lệ. Nỗ lực nhỏ này thường có thể khám phá ra một chi tiết quan trọng trong quá trình gỡ lỗi. WilberWorks đã chuyển báo trang lỗi của tôi thành một trang hỗ trợ.

Rõ ràng, WilberWorks tồn tại để kiếm tiền. Vậy tại sao lại có hệ thống theo dõi lỗi? Câu trả lời rất đơn giản - nó mang lại lợi nhuận và họ cũng không mất gì cả. Ngoài việc giúp cho sản phẩm cuối tốt hơn, họ còn đưa ra chính sách sửa bất kỳ lỗi nào trong vòng 10 ngày nếu bạn có hợp đồng hỗ trợ. Bởi vì họ có các nhà phát triển với kiến ​​thức sâu rộng về hệ thống và có kĩ năng thành thạo, WilberWorks cảm thấy rằng chính sách này là hoàn toàn thực hiện được. Điều này cũng khiến họ khác biệt, bởi vì bạn sẽ khó tìm thấy điều tương tự ở một ứng dụng thương mại ớn khác.

## Tập trung hóa

Để đáp ứng nhu cầu về một kho lưu trữ trung tâm cho tất cả các khía cạnh của chương trình, Shawn Amundson (Snorfle) đã lấy miền “gimp.org”. Máy chủ chính của trang này là [www.gimp.org](www.gimp.org){:target="_blank"}, rất dễ nhớ và dễ đoán giả sử bạn có quên hoặc không biết. Bắt đầu vào ngày 7 tháng 10 năm 1997, nó cung cấp tổng quan về những điều cần thiết để bạn làm quen với GIMP, từ mã nguồn cho đến các mẹo và thủ thuật.

## Được biết đến nhiều hơn

Michael J. Hammel đã viết một loạt bài bốn phần về GIMP để đưa vào Tạp chí Linux (tháng 10 năm 1997 - tháng 1 năm 1998). Nó đã giới thiệu một số khái niệm cơ bản, nhưng chỉ dừng lại ở các đặc điểm nổi bật của GIMP. Tuy nhiên, với chất lượng viết tốt và chính xác, loạt bài này đã đưa với cộng đồng Linux (và bất kỳ ai đọc tài liệu về cộng đồng linux) đến với GIMP. GIMP cũng được giới thiệu thông qua bài báo Graphics Muse của anh ấy trên tờ Linux Gazette .

Red Hat Linux đã đóng gói GIMP đi kèm trong bản phân phối của distro này kể từ phiên bản 5.0. Điều này hóa ra là một con dao hai lưỡi - trong khi nó đưa GIMP đến với thế giới, nó lại đồng thời là phiên bản cũ của GIMP. Nếu bạn đang sử dụng phiên bản 0.99.12 đi kèm với RedHat 5.0, vui lòng nâng cấp ngay! Nhiều cải tiến đối với thư viện, chương trình và plug-in thêm đã diễn ra kể từ phiên bản 0.99.12.

[www.gimp.org](www.gimp.org){:target="_blank"} cũng sử dụng linh vật của GIMP, Wilber. Wilber khá tuyệt. Đôi mắt của Wilber chuyển động, và điều đó hơi khó chịu với một số người, nhưng tôi thích thế. Wilber, tất nhiên, được tạo ra bằng GIMP. Được tạo ra vào ngày 25 tháng 9 năm 1997 bởi Tuomas Kuosmanen, Wilber đã có một cuộc sống của riêng mình. Ví dụ, trong hình Wilber đang làm đủ thứ việc ở góc trên cùng bên trái của trang tại [www.gimp.org](www.gimp.org){:target="_blank"} (chỉnh sửa: trang web cũ hiện có tại [classic.gimp.org](classic.gimp.org){:target="_blank"}). Wilber đã trở thành một biểu tượng được công nhận gắn liền với GIMP và có thể được nhìn thấy trên [slashdot](http://slashdot.org/){:target="_blank"} bất cứ khi nào GIMP được đề cập đến. Cậu ấy xuất hiện trên màn hình trợ giúp khi khởi động GIMP lần đầu tiên, đưa ra vài lời khuyên hữu ích. Bây giờ thì GIMP phổ biến đối với người dùng, Wilber đang giúp đưa GIMP đến với đông đảo công chúng giống như (chim cánh cụt) Tux đối với cho Linux.

## Và mọi chuyện vẫn tiếp tục

Nhớ GTK+ chứ? Một số nhà phát triển có ý tưởng điên rồ rằng nó thực sự là một bộ công cụ tuyệt vời và nên được phổ biến. Và chúng ta có thể tạo một môi trường làm việc nền dựa trên bộ công cụ này. Giống như nhiều ý tưởng điên rồ khác, điều này đang trở thành hiện thực. Dự án GNOME đang thực hiện, và đang trong giai đoạn alpha. Dự án GNOME được hỗ trợ tích cực bởi Red Hat Labs. Tất cả những điều này có thể được coi là hệ quả của của GIMP. Sự thành công của một dự án này đã sinh ra nhiều dự án khác.

Vào ngày 5 tháng 6 năm 1998, lúc 17:17 CST , GIMP 1.0 được phát hành. Những kế hoạch tuyệt vời cho tương lai đang hình thành ngay từ bây giờ!

