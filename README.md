# main
dem-so-tu-trong-chuoi-c-c
void Correct(char str[], int length)
{
    int first = 0, last = length - 1;
    // Xóa dấu trắng đầu chuỗi
    while (first < last && str[first] == ' ')
        first++;
    // Xóa dấu trắng cuối chuỗi
    while (last > first && str[last] == ' ')
        last--;

    // Viết hoa chữ cái đầu tiên
    if (str[first] >= 'a' && str[first] <= 'z')
        str[first] -= 32;
    for (int i = first + 1; i <= last; i++)
    {
        // Đưa hết về chữ thường
        if (str[i] >= 'A' && str[i] <= 'Z'){
            str[i] += 32;
        }
        if (i + 1 <= last)
        {
            // Bỏ dấu trắng thừa ở giữa
            if (str[i] == str[i + 1] && str[i] == ' ')
            {
                continue;
            }
            // Nếu là chữ cái đầu mỗi từ thì viết hoa
            if (str[i] == ' ' && str[i + 1] >= 'a' && str[i + 1] <= 'z')
            {
                str[i + 1] -= 32;
            }
        }
        printf("%c", str[i]);
    }
}
