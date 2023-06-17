# Regularization-Concepts

This project provides a brief demonstration on Ridge and Lasso regression techniques.

## Background

The project focuses on linear regression and aims to predict salary (y) based on years of experience (x). The training data consists of two data points, and the goal is to find the best fit line that passes through both points.

[Training data.png](data:image/png;base64,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)

## Ridge Regression

Ridge regression is a regularization technique that helps to mitigate overfitting in linear regression models. It introduces a penalty term to the loss function, which controls the complexity of the model. By adding a regularization term, Ridge regression limits the impact of the predictor variables, preventing them from having extreme values.

## Lasso Regression

Similar to Ridge regression, Lasso regression is another regularization technique used to prevent overfitting in linear regression models. Lasso regression also adds a penalty term to the loss function, but it uses the L1 norm of the coefficients. This regularization technique encourages sparsity in the model by driving some of the coefficients to zero, effectively selecting a subset of the most important features.

## Usage

To run this project and explore the demonstration of Ridge and Lasso regression:

1. Install the required dependencies (e.g., Python, scikit-learn, matplotlib).
2. Clone the project repository: `git clone https://github.com/username/project.git`
3. Navigate to the project directory: `cd project`
4. Explore the code and modify the data points or parameters as desired.
5. Run the script or notebook to see the visual representation and analysis of Ridge and Lasso regression on the provided dataset.

Feel free to customize the code and experiment with different datasets to further understand the impact of regularization techniques on linear regression models.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
