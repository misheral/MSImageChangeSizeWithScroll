# MSImageChangeSizeWithScroll
Objective-C，下拉列表时修改表头图片的大小，滚动视图的delegat方法内实现view的frame修改。
...

- (void)scrollViewDidScroll:(UIScrollView *)scrollView{
    CGPoint point = scrollView.contentOffset;
    CGFloat offsetY = point.y;
    CGRect rect = self.headerView.frame;
    if (offsetY <= 0) {
        offsetY = offsetY < -kTableHeaderImageHeight ? offsetY : -kTableHeaderImageHeight;
        rect.origin.y = offsetY;
        rect.size.height = -offsetY;
    }
    self.headerView.frame = rect;
}

...

不想修改ssh，所以没有上传代码，只是打包了一个完整的prj，直接下载下来运行即可。

