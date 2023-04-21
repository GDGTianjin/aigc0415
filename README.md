# 人工智能技术应用分享沙龙-2023.04.15
其中GDE林嵩老师分享的内容一个自己动手搭建* Keras + Stable Diffusion *环境跑AIGC一个demo的例子，具体步骤如下：
**注：这个例子因为使用某些高版本tf才有的函数，所以要求tf在2.12以上**

**步骤**

1. 按照https://tensorflow.google.cn/install/pip#linux_1或wsl2的Step-by-step instructions安装tf 2.12.*（这个说明恰好是针对所需要的tf版本，所以cuda和cudnn都可以直接采用这里面的版本），注意要看英文版说明，安装成功应该可以看到GPU device。（我用的ubuntu20.05）*
2. *保持在上一步的虚拟环境里，安装keras_cv 0.4.*，tf_database，jupyter， 其中keras_cv 运行需要pip install pycocotools，而安装pycocotools需要sudo apt-get install gcc， 而这又可能需要sudo apt-get update，我是这个流程装的，是不是不妨也可以反过来（*gcc和update退回到base环境操作*）。jupyter运行需要安装浏览器（如firefox）
3. 正常来说，这时候这个例子https://keras.io/guides/keras_cv/generate_images_with_stable_diffusion/
   就应该可以运行了，需要先下几个权重文件（*如果没有预先下载的话，当然预先下载之后需要在models里面改路径*）
4. 4个文件下载路径
   - https://github.com/openai/CLIP/blob/main/clip/bpe_simple_vocab_16e6.txt.gz?raw=true   *这个可能需要改个文件名，\b转码会出错*
   - https://huggingface.co/fchollet/stable-diffusion/resolve/main/kcv_decoder.h5
   - https://huggingface.co/fchollet/stable-diffusion/resolve/main/kcv_encoder.h5
   - https://huggingface.co/fchollet/stable-diffusion/resolve/main/kcv_diffusion_model.h5

