<div align="center"> <h2>Realistic Surgical Image Augmentation image-to-image domain transfer by Generative Adversarial Nets (GANs) </h2> </div>

<div align="center"> <h4>Melody Su(1), Wenfan Jiang(1), Haonan Peng(2) </h4> </div>

<div align="center"> <h4>(1) Department of Computer Science, Mount Holyoke College </h4> </div>
<div align="center"> <h4>(2) Department of Electrical and Computer Engineering, University of Washington </h4> </div>

Surgical tool segmentation is a key component of numerous computer-assisted interventions\[1\]. Due to the challenges of dynamic deformation, specular reflections, and partial blurriness\[2\], it often requires large surgical image datasets to achieve desirable segmentation performances using data-driven approaches. However, since large surgical image datasets are expensive and sometimes even impractical to acquire from clinical robot assisted surgeries\[3\] because of the potential interruption of surgical workflows, as well as sterilization and data privacy concerns, our group implemented a realistic surgical image augmentation framework based on GANs (Generative Adversarial Networks)\[4\].
In this proposed model, the authors created a CycleGAN\[5\]-like structure with four loss functions.
The image level losses, (1) the cycle-consistency loss and (2) the GAN loss, were designed to preserve the semantic meaning of the whole image; meanwhile, the component-level loss functions such as (3) the style loss of tool and (4) the content loss of tissue, trace back in the hidden layer activations to perform deep restricted style transfer locally in the surgical tool region of the images while ensuring minimal modifications to the background. The separation of foreground and background were provided in the dataset as prior knowledge. Specifically, the authors trained the proposed model on two sets of pre-segmented images, the UW Sinus Surgery Cadaver/Live Dataset\[6\] alongside a baseline fake surgical image generator which constructs mass, unrealistic augmented surgical images\[7\]. In addition, the performances of four slightly different GAN inspired framework were comparatively showcased, demonstrating that this proposed framework outperforms the others. The first approach was to naively train CycleGAN\[5\] on raw images. In the second iteration, images were preprocessed to standardize image quality and border consistency. The authors also tried to conduct local GAN training only in the surgical tool portion, but ultimately the best result was obtained using proposed the partial style preservation framework. As a next step, the authors will test the proposed GAN-based artificial surgical image generator by evaluating whether a state-of-the-art surgical tool segmentation model\[8\] can be trained on our artificial surgical images and perform well on real surgical images during test time.

### References:
\[1\] Delp, Scott L., et al. "Computer-assisted surgical system." U.S. Patent No. 5,682,886. 4 Nov. 1997.

\[2\] Hesamian, Mohammad Hesam, et al. "Deep learning techniques for medical image segmentation: Achievements and challenges." Journal of digital imaging 32.4 (2019): 582-596.

\[3\] Colleoni, Emanuele, Philip Edwards, and Danail Stoyanov. "Synthetic and Real Inputs for Tool Segmentation in Robotic Surgery." International Conference on Medical Image Computing and Computer-Assisted Intervention. Springer, Cham, 2020.

\[4\] Liu, Ming-Yu, Thomas Breuel, and Jan Kautz. "Unsupervised image-to-image translation networks." Advances in neural information processing systems. 2017.

\[5\] Jun-Yan Zhu, Taesung Park, Phillip Isola, and Alexei A. Efros. "Unpaired Image-to-Image Translation using Cycle-Consistent Adversarial Networks", in IEEE International Conference on Computer Vision (ICCV), 2017.

\[6\] Lin, Shan, et al. "UW Sinus Surgery Cadaver/Live Dataset (UW-Sinus-Surgery-C/L)." (2020).

\[7\] This is a software package Haonan developed and shared for our research study.

\[8\] Garcia-Peraza-Herrera, Luis C., et al. "Toolnet: holistically-nested real-time segmentation of robotic surgical tools." 2017 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS). IEEE, 2017.
