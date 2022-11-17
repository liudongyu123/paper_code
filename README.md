
## Quick Start

<details>
<summary>Installation</summary>

Step1. Install YOLOX from source.
```shell
git clone https://github.com/liudongyu123/paper.git
cd YOLOX
pip3 install -v -e .
```
训练：
python -m yolox.tools.train -f exps/asl_detection/yolox_s.py -d 1 -b 32 --fp16 -o --exp_name 名字
推理：
python -m yolox.tools.eval -f exps/default/yolox_s.py -c ./YOLOX_outputs/yolox_s/best_ckpt.pth -b 32 -d 1 --fp16 -expn 名字
演示：（ASL）
python tools/demo.py image -f exps/default/yolox_s.py -c ./YOLOX_outputs/yolox_s/best_ckpt.pth --path assets/A22_asl.jpg --conf 0.25 --nms 0.45 --tsize 416 --save_result --device gpu -expn eval_asl

python tools/demo.py image -n yolox-s -c ./YOLOX_outputs/yolox_s/best_ckpt.pth --path assets/A22_asl.jpg --conf 0.25 --nms 0.45 --tsize 416 --save_result --device gpu -expn eval_asl

