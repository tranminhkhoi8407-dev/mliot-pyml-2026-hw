# Homework B13: MLP phân loại EMNIST

Hoàn thành các phần `TODO` trong notebook [pytorch_emnist.ipynb](pytorch_emnist.ipynb) để xây dựng pipeline huấn luyện mạng MLP phân loại 26 chữ cái in hoa A–Z của bộ dữ liệu EMNIST (`split='letters'`).

## Yêu cầu

1. **Cấu hình**: khai báo `BATCH_SIZE`, `EPOCHS`, `LEARNING_RATE`, `DATA_DIR` và chọn `DEVICE` (`cuda` nếu khả dụng, nếu không dùng `cpu`). .
2. **Dữ liệu**: tải EMNIST bằng `torchvision`, chuyển ảnh sang tensor, tách 124.800 mẫu train gốc thành 100.000 mẫu train và 24.800 mẫu validation; tạo `train_loader`, `val_loader`, `test_loader`. Chỉ train loader được xáo trộn dữ liệu.
3. **Khám phá dữ liệu**: in kích thước một batch và vẽ 10 ảnh đầu tiên. Đổi nhãn 0–25 sang ký tự A–Z khi hiển thị.
4. **Mô hình**: cài đặt lớp `EMNISTMLP(nn.Module)` theo kiến trúc tối thiểu `Flatten → Linear(784, 128) → ReLU → Linear(128, 26)`.
5. **Huấn luyện và đánh giá**: hoàn thiện `train_one_epoch` và `evaluate`. Hàm train cần cập nhật trọng số; hàm evaluate dùng `model.eval()` và `torch.no_grad()`; cả hai trả về loss trung bình và accuracy.
6. **Theo dõi kết quả**: huấn luyện qua các epoch, lưu train/validation loss và accuracy, đồng thời in kết quả mỗi epoch.
7. **Đánh giá cuối**: vẽ biểu đồ Loss và Accuracy theo epoch (train so với validation), đánh giá trên `test_loader`, rồi vẽ 10 ảnh test với nhãn thật và dự đoán (xanh nếu đúng, đỏ nếu sai).
8. **Lưu mô hình**: lưu `state_dict` vào file `emnist_mlp.pt`.

## Kết quả mong đợi

MLP cơ bản thường đạt khoảng **85–90% test accuracy**. Đây là mốc tham khảo; hãy báo cáo accuracy thực tế thu được khi chạy notebook.

## Nộp bài

Nộp notebook đã hoàn thành, có đầy đủ output của quá trình huấn luyện, biểu đồ và kết quả test.
