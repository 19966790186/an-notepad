def create_note():
    title = input("输入笔记文件名：")
    content = input("输入笔记内容：")
    with open(f"{title}.txt", "w", encoding="utf-8") as f:
        f.write(content)
    print(f"笔记 {title}.txt 创建完成！")

def read_note():
    title = input("输入要读取的笔记名：")
    try:
        with open(f"{title}.txt", "r", encoding="utf-8") as f:
            print("\n笔记内容：\n", f.read())
    except FileNotFoundError:
        print("文件不存在")

if __name__ == "__main__":
    print("1.新建笔记  2.读取笔记")
    opt = input("请选择功能：")
    if opt == "1":
        create_note()
    elif opt == "2":
        read_note()
