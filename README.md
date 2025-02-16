# ECGR-5106 Homework 2

## Student Information
**Name:** Yang Xu  
**Student ID:** 801443244  
**Homework Number:** 2  

## GitHub Repository
[https://github.com/xuy50/ecgr5106-hw2](https://github.com/xuy50/ecgr5106-hw2)

---

## Problem 1: AlexNet on CIFAR-10 and CIFAR-100

### **1.a Original and Simplified AlexNet**
I implemented both the original AlexNet and a simplified version adapted for CIFAR-10 and CIFAR-100 datasets. The goal was to make the training more efficient while maintaining competitive accuracy.

#### **Network Details:**
- **Original AlexNet**: 5 convolutional layers, 3 fully connected layers, total parameters **23,272,266**.
- **Simplified AlexNet**: 3 convolutional layers, 2 fully connected layers, total parameters **620,362**.

#### **Training and Validation Results (CIFAR-10)**
| Model                  | Dropout | Final Train Loss | Final Val Loss | Val Accuracy |
|------------------------|---------|------------------|----------------|--------------|
| Original AlexNet      | No      | 0.5735           | 0.7400         | 75.66%       |
| Original AlexNet      | Yes     | 1.0920           | 1.1594         | 64.48%       |
| Simplified AlexNet    | No      | 0.4182           | 0.6253         | 79.86%       |
| Simplified AlexNet    | Yes     | 0.4876           | 0.6891         | 76.20%       |

#### **Training and Validation Results (CIFAR-100)**
| Model                  | Dropout | Final Train Loss | Final Val Loss | Val Accuracy |
|------------------------|---------|------------------|----------------|--------------|
| Original AlexNet      | No      | 1.8342           | 2.6812         | 35.32%       |
| Original AlexNet      | Yes     | 3.3233           | 3.3519         | 19.76%       |
| Simplified AlexNet    | No      | 1.2021           | 2.4153         | 42.15%       |
| Simplified AlexNet    | Yes     | 1.3460           | 2.5679         | 39.50%       |

#### **Evaluation Metrics (CIFAR-10, Original AlexNet)**
| Model                  | Precision | Recall | F1 Score |
|------------------------|-----------|--------|----------|
| Without Dropout       | 0.7688    | 0.766  | 0.7648   |
| With Dropout         | 0.7059    | 0.6716 | 0.6753   |

#### **Observations:**
- The simplified AlexNet performed comparably to the original AlexNet with **far fewer parameters**.
- Adding dropout improved generalization but slightly reduced validation accuracy.
- CIFAR-100 was significantly more challenging than CIFAR-10 due to its larger number of classes.

#### **Training and Validation Loss & Accuracy Plots:**
- ![Original AlexNet Results (CIFAR-10)](./images/p1_10_original_alexnet_results.png)
- ![Simplified AlexNet Results (CIFAR-10)](./images/p1_10_simplified_alexnet_results.png)
- ![Original AlexNet Results (CIFAR-100)](./images/p1_100_original_alexnet_results.png)
- ![Simplified AlexNet Results (CIFAR-100)](./images/p1_100_simplified_alexnet_results.png)

---

## Problem 2: VGG on CIFAR-10 and CIFAR-100

### **2.a VGG Configuration Selection**
The goal was to select a VGG configuration with a parameter count close to AlexNet. VGG-11 was chosen as it has a similar number of parameters.

#### **Training and Validation Results (CIFAR-10)**
| Model      | Dropout | Final Train Loss | Final Val Loss | Val Accuracy |
|-----------|---------|------------------|----------------|--------------|
| VGG-11   | No      | 0.4315           | 0.6032         | 78.45%       |
| VGG-11   | Yes     | 0.5102           | 0.6501         | 75.30%       |

#### **Training and Validation Results (CIFAR-100)**
| Model      | Dropout | Final Train Loss | Final Val Loss | Val Accuracy |
|-----------|---------|------------------|----------------|--------------|
| VGG-11   | No      | 1.8421           | 2.6123         | 37.22%       |
| VGG-11   | Yes     | 2.1023           | 2.8912         | 33.10%       |

#### **Observations:**
- VGG-11 achieved similar accuracy as AlexNet but took longer to train due to deeper architecture.
- Dropout had a noticeable effect in preventing overfitting but slightly reduced validation accuracy.

#### **Training and Validation Loss & Accuracy Plots:**
- ![VGG-11 Results (CIFAR-10)](./images/p2_10_vggnet_results.png)
- ![VGG-11 Results (CIFAR-100)](./images/p2_100_vggnet_results.png)

---

## Problem 3: ResNet-11 vs ResNet-18 on CIFAR-10 and CIFAR-100

### **3.a Comparing ResNet Architectures**
I implemented both ResNet-11 and ResNet-18 and compared their performance.

#### **Training and Validation Results (CIFAR-10)**
| Model      | Dropout | Final Train Loss | Final Val Loss | Val Accuracy |
|-----------|---------|------------------|----------------|--------------|
| ResNet-11 | No      | 0.3312           | 0.4897         | 82.12%       |
| ResNet-11 | Yes     | 0.4121           | 0.5323         | 80.05%       |
| ResNet-18 | No      | 0.2914           | 0.4501         | 85.43%       |
| ResNet-18 | Yes     | 0.3512           | 0.4923         | 83.22%       |

#### **Training and Validation Results (CIFAR-100)**
| Model      | Dropout | Final Train Loss | Final Val Loss | Val Accuracy |
|-----------|---------|------------------|----------------|--------------|
| ResNet-11 | No      | 1.4012           | 2.2313         | 42.32%       |
| ResNet-11 | Yes     | 1.6102           | 2.5012         | 38.10%       |
| ResNet-18 | No      | 1.1921           | 2.0124         | 45.89%       |
| ResNet-18 | Yes     | 1.3421           | 2.3201         | 42.80%       |

#### **Observations:**
- ResNet-18 performed significantly better than ResNet-11, confirming that deeper networks improve feature learning.
- Dropout was useful in preventing overfitting, but at the cost of slightly lower accuracy.

#### **Training and Validation Loss & Accuracy Plots:**
- ![ResNet-11 Results (CIFAR-10)](./images/p3_10_ResNet11_results.png)
- ![ResNet-18 Results (CIFAR-10)](./images/p3_10_ResNet18_results.png)
- ![ResNet-11 Results (CIFAR-100)](./images/p3_100_ResNet11_results.png)
- ![ResNet-18 Results (CIFAR-100)](./images/p3_100_ResNet18_results.png)

---

### **Final Conclusion**
- **Simplified AlexNet performed comparably to the original with far fewer parameters.**
- **VGG-11 achieved similar results to AlexNet but required more computation.**
- **ResNet-18 significantly outperformed ResNet-11, confirming the benefits of deeper architectures.**

