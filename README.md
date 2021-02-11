

<!-- PROJECT LOGO -->
<p align="center">
    <a href="https://paip2020.grand-challenge.org">
        <img src="data/images/logo.jpg" alt="Logo">
    </a>
    <h3 align="center">PAIP2020</h3>
    <p align="center"> 
        PAIP2020 is the second challenge organized by the Pathology AI Platform (PAIP) <br>and the Seoul National University Hospital (SNUH).
    <br>
        <a href="https://paip2020.grand-challenge.org"><strong>PAIP2020 homepage</strong></a>
    </p>      
</p>



<!--Table of Contents--!>

<strong>Table of contents</strong>
<details open="open">
    <ol>
        <li>
            PAIP2020 Challenge
            <ul>
                <li>Aims</li>
                <li>background</li>
                <li>dataset</li>
                <li>evaluation</li>
            </ul>
        </li>
        <li>
            Our method
            <ul>
                <li>preprocessing</li>
                <li>pretrained model</li>
                <li>training</li>
                <li>inference</li>
            </ul>
        </li>
        <li>
            Installation
        </li>
        <li>
            prerequisites
        </li>
    </ol>
</details>



<!--PAIP2020 challenge-->
## PAIP2020 Challenge

<ul>
    <li><strong>Aims:</strong></li>
    &nbsp;
    <li><strong>background:</strong></li>
    &nbsp;
    <li><strong>dataset</strong></li>
    &nbsp;
    <li><strong>evaluation</strong></li>
    &nbsp;
</ul>


<!-- ABOUT THE PROJECT -->
## Our method
<p align="center">
    <img src="data/images/overview.PNG" alt="overview">
    <h5 align="center">Figure1.Overview</h5>
</p>
<ol>
    <li><strong>Task1</strong></li>
    &nbsp;
    Task1 includes 3 different kinds of images, including the original WSIs, tissue masks for the WSIs, and tumor masks for the WSIs. The tissue masks are generated by using a threshold value (220, 200, 220) in RGB. The tumor masks are supplied either by ground truth or by Task2.All the tissue masks, tumor masks, and original WSIs are resized to x5 magnification. Using the tissue and tumor masks, tumor tiles of size 256x256 pixels are created as long as the tiles possess >80% of tumor area and >60% of tissue area. Given the tumor tiles of each WSI, N2 tiles (N=10) are randomly selected and undergo image augmentation, including scaling, translating, and shearing. Then, the tiles are cropped to the size of 128x128 pixels. The N2 tiles are reshaped into a rectangular image patch of size 1280x1280 pixels and used to train a CNN model (efficientnet-b0) for MSI-High classification. During testing, 1000 image patches are generated for each WSI and the CNN model classify the patches. Summarizing the results via majority voting, we predict the class label for the WSI. 

</ol>

<!--prerequisites-->
## prerequisites
imgaug
torch
openslide-python
tiffile

<!--certification-->
## certification
<p align="center">
    <img src="data/images/certicification.PNG" alt="Logo" width="70%" >

</p>


