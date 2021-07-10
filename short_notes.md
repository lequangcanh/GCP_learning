* Có thể generate 10 access keys cho mỗi service account
* StatefulSet (K8s) đại diện cho tập hợp của các Pod, nó như là 1 Pod template, nó sử dụng một thứ tự index được order để triển khai các pod. Pod đầu tiên dc tạo sẽ đánh dấu là `name-0` (mặc định sẽ là master), các pod tiếp theo sẽ theo thứ tự `name-1`, `name-2`, ... Khi tắt thì tắt theo thứ tự ngược lại
* Dataproc cung cấp 1 Hadoop cluster, và truy cập vào hệ sinh thái của Hadoop
* Dataflow cung cấp một nơi để run các Apache Beam jobs, serverless
* Sau khi request tạo 1 instance mới (Service account phải được tạo trước khi attach vào instance), instance sẽ được bắt đầu ở trạng thái Provisioning. Sau khi space được tìm thấy và gán vào host machine, instance sẽ được chuyển sang trạng thái Starting, trong khi host machine chuẩn bị run instance và sắp xếp lại một số thứ như network adapter, ... Ngay khi VM được khoier động lên và hệ điều hành chạy các start up scripts, instance sẽ chuyển sang trạng thái Running
* GAE ko support GPUs. Chỉ có GKE và GCE
* Service account được sử dụng bởi các programs và chúng là 1 cách để quản lý resource, nhưng không phải là cách duy nhất
* Trong instance type, RAM sẽ gấp đôi theo số CPU, nhưng số lượng ít nhiều sẽ theo thứ tự highcpu < standard < highmem
* Data Studio là tool cho phép xem được lịch sử cost một cách trực quan
* Enable 1 service từ Cloud Shell, `gcloud services enable xyz.googleapis.com`
* Persistent Disk có thể attach vào GCE và GKE
* Mặc định khi tại GCE sẽ tạo 1 service account mặc định. Tuy nhiên có thể remove service account này ra khỏi VM bằng cách xóa nó đi hoặc không chọn đính kém serivce account khi tạo VM
* GAE mặc định connect tới Stackdriver và send cả request logs lẫn application logs cho nó
