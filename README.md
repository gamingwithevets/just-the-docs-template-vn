# just-the-docs-template-vn

*(được dịch từ bản tiếng Anh, liên kết vẫn ra trang tiếng Anh nhé!)*

Đây là mẫu *tối thiểu* để tạo trang web [Jekyll]:

- sử dụng theme [Just the Docs];
- có thể được xây dựng và xuất bản trên [GitHub Pages];
- có thể được xây dựng và xem trước cục bộ và xuất bản trên các nền tảng khác.

Cụ thể hơn, trang web đã tạo:

- sử dụng cách tiếp cận dựa trên gem, tức là sử dụng `Gemfile` và tải gem `just-the-docs`;
- sử dụng [workflow GitHub Pages / Actions] để xây dựng và xuất bản trang web trên Trang GitHub.

Để bắt đầu tạo một trang web, chỉ cần nhấp vào "[use this template]"!

Nếu bạn muốn duy trì tài liệu của mình trong thư mục `docs` của repository dự án hiện có, hãy xem phần [Lưu trữ tài liệu của bạn từ repository dự án hiện có](#lưu-trữ-tài-liệu-của-bạn-từ-repository-dự-án-hiện-có).

Sau khi hoàn thành việc tạo trang web mới của bạn trên GitHub, hãy cập nhật nó nếu cần:

## Thay thế nội dung của các trang mẫu

Cập nhật các tệp sau thành nội dung của riêng bạn:

- `index.md` (trang chủ mới của bạn)
- `README.md` (thông tin dành cho những ai truy cập repository của trang web của bạn trên GitHub)

## Thay đổi phiên bản của chủ đề và/hoặc Jekyll

Chỉ cần chỉnh sửa (các) dòng có liên quan trong `Gemfile`.

## Thêm plugin

Chủ đề Just the Docs tự động bao gồm plugin [`jekyll-seo-tag`].

Để thêm một plugin bổ sung, bạn cần thêm nó vào `Gemfile` *và* trong `_config.yml`. Ví dụ: để thêm [`jekyll-default-layout`]:

- Thêm phần này vào `Gemfile` của trang web của bạn:

   ```ruby
   gem "jekyll-default-layout"
   ```

- Và thêm phần này vào `_config.yml` của trang web của bạn:

   ```yaml
   plugins:
     - jekyll-default-layout
   ```

Lưu ý: Nếu bạn đang sử dụng phiên bản Jekyll cũ hơn 3.5.0, hãy sử dụng key `gems` thay vì `plugins`.

## Xuất bản trang web của bạn trên Trang GitHub

1. Nếu trang web đã tạo của bạn là `TÊN-NGƯỜI-DÙNG/TÊN-TRANG-WEB`, hãy cập nhật `_config.yml` thành:

     ```yaml
     title: TIÊU ĐỀ CỦA BẠN
     description: MÔ TẢ CỦA BẠN
     theme: just-the-docs
	 
     url: https://TÊN-NGƯỜI-DÙNG.github.io/TÊN-TRANG-WEB 
     aux_links: # xóa nếu bạn không muốn liên kết này xuất hiện trên các trang của mình
       Xem repository trên GitHub: https://github.com/TÊN-NGƯỜI-DÙNG/TÊN-TRANG-WEB
     ```

2. Đẩy `_config.yml` đã cập nhật vào trang web của bạn trên GitHub.

3. Trong repo mới tạo của bạn trên GitHub:
     - chuyển đến tab `Settings` -> `Pages` -> `Build and deployment`, sau đó chọn `Source`: `GitHub Actions`.
     - nếu có bất kỳ Action nào không thành công, hãy chuyển đến tab `Actions` và nhấp vào `Re-run jobs`.

## Xây dựng và xem trước trang web của bạn cục bộ

Giả sử [Jekyll] và [Bundler] được cài đặt trên máy tính của bạn:

1. Thay đổi thư mục làm việc của bạn thành thư mục gốc của trang web của bạn.

2. Chạy lệnh `bundle install`.

3. Chạy lệnh `bundle exec jekyll serve` để xây dựng trang web của bạn và xem trước tại `localhost:4000`.

     Trang web đã xây dựng được lưu trữ trong thư mục `_site`.

## Xuất bản trang web đã xây dựng của bạn trên một nền tảng khác

Chỉ cần tải lên tất cả các tệp trong thư mục `_site`.

## Tùy chỉnh

Bạn được tự do tùy chỉnh các trang web mà bạn tạo bằng mẫu này, theo bất kỳ cách nào bạn muốn!

[Xem tài liệu của chúng tôi][Just the Docs] để tìm hiểu thêm về cách sử dụng chủ đề này.

## Lưu trữ tài liệu của bạn từ repository dự án hiện có

Bạn có thể muốn duy trì tài liệu của mình trong kho dự án hiện có. Thay vì tạo một repository mới bằng [mẫu just-the-docs](https://github.com/just-the-docs/just-the-docs-template), bạn có thể sao chép các tệp mẫu vào repository hiện có của mình và định cấu hình luồng công việc Github Actions của mẫu để xây dựng từ thư mục `docs`. Bạn có thể sao chép mẫu vào máy cục bộ của mình hoặc tải xuống tệp `.zip` để truy cập các tệp.

### Sao chép tệp mẫu

1. Tạo thư mục `.github/workflows` tại gốc dự án của bạn nếu repository của bạn chưa có. Sao chép tệp `pages.yml` vào thư mục này. GitHub Actions sẽ tìm kiếm tệp workflow trong thư mục này.

2. Tạo một thư mục `docs` tại gốc dự án của bạn và sao chép tất cả các tệp mẫu còn lại vào thư mục này.

### Sửa đổi quy trình làm việc của GitHub Actions

Workflow GitHub Actions xây dựng và triển khai trang web của bạn lên GitHub Actions được xác định bởi tệp `pages.yml`. Bạn sẽ cần chỉnh sửa tệp này để các bước build và deploy của bạn nhìn vào thư mục `docs` của bạn, thay vì thư mục gốc của dự án.

1.  Đặt tham số `working-directory` mặc định cho build job.

    ```yaml
    build:
      runs-on: ubuntu-latest
      defaults:
        run:
          working-directory: docs
    ```

2.  Đặt tham số `working-directory` cho bước Setup Ruby.

    ```yaml
    - name: Setup Ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: '3.1'
          bundler-cache: true
          cache-version: 0
          working-directory: '${{ github.workspace }}/docs'
    ```

3.  Đặt tham số path cho bước Upload artifact:

    ```yaml
    - name: Upload artifact
        uses: actions/upload-pages-artifact@v1
        with:
          path: "docs/_site/"
    ```

4.  Sửa đổi trình kích hoạt để chỉ những thay đổi trong thư mục `docs` mới bắt đầu workflow. Mặt khác, mọi thay đổi đối với dự án của bạn (ngay cả những thay đổi không ảnh hưởng đến tài liệu) sẽ kích hoạt việc build và deploy trang web mới.

    ```yaml
    on:
      push:
        branches:
          - "main"
        paths:
          - "docs/**"
    ```

## Cấp phép và Ghi công

Kho lưu trữ này được cấp phép theo [Giấy phép MIT]. Nói chung, bạn được tự do sử dụng lại hoặc mở rộng mã này khi bạn thấy phù hợp; chỉ bao gồm bản gốc của giấy phép (được giữ nguyên khi bạn "làm tiêu bản"). Mặc dù không cần thiết nhưng chúng tôi muốn nghe ý kiến từ bạn nếu bạn sử dụng mẫu này và cách chúng tôi có thể cải thiện mẫu để sử dụng trong tương lai!

Workflow triển khai GitHub Actions chủ yếu dựa trên [starter workflow] bên hỗn hợp của GitHub. Bản sao Giấy phép MIT của họ có sẵn trong [actions/starter-workflows].

----

[^1]: [Có thể mất tối đa 10 phút để các thay đổi đối với trang web của bạn xuất bản sau khi bạn đẩy các thay đổi lên GitHub](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll#creating-your-site).

[Jekyll]: https://jekyllrb.com
[Just the Docs]: https://just-the-docs.github.io/just-the-docs/
[GitHub Pages]: https://docs.github.com/en/pages
[workflow GitHub Pages / Actions]: https://github.blog/changelog/2022-07-27-github-pages-custom-github-actions-workflows-beta/
[Bundler]: https://bundler.io
[use this template]: https://github.com/just-the-docs/just-the-docs-template/generate
[`jekyll-default-layout`]: https://github.com/benbalter/jekyll-default-layout
[`jekyll-seo-tag`]: https://jekyll.github.io/jekyll-seo-tag
[Giấy phép MIT]: https://en.wikipedia.org/wiki/MIT_License
[starter workflow]: https://github.com/actions/starter-workflows/blob/main/pages/jekyll.yml
[actions/starter-workflows]: https://github.com/actions/starter-workflows/blob/main/LICENSE