监控Express4代码变化自动加载 之前使用Express3时,使用supervisor来启动应用,当代码发生变化时会自动加载.

下载换到了Express4上,原来在Express3上能工作的好多都不起作用了.例如:
Express3启动应用使用: node app Express4启动应用使用: node ./bin/www 或者 DEBUG=projectName ./bin/www

如果不能监测代码变化,自动加载,每次修改都要手动重启,这回让人疯掉的.在网上找到一篇博客,完美的解决了这个问题,在这里记录一下.

相比 supervisor ，nodemon 的优点包括：更轻量级，内存占用更小。使用更加方便，更容易进行扩展等。

nodemon 的使用方法与 supervisor 相似， npm install -g nodemon 直接运行nodemon app.js即可，
可以随时输入rs回车进行手动重启，非常方便。 更多的使用方法可以在它的 github主页 找到。

Express 4.x 默认将启动模块分离到了./bin/www中，直接使用 supervisor 无法正常监控应用，使得开发过程中的调试非常不方便。

nodemon app.js 进行调试了