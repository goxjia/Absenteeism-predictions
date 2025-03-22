# 员工缺勤预测系统

## 项目简介
这是一个基于员工信息和工作数据的缺勤预测工具。通过分析员工的通勤费用、工作量、教育程度等12+个字段，使用机器学习模型预测员工的缺勤概率，帮助企业更好地管理员工出勤情况。

## 主要功能
1. **数据处理**：自动清洗数据，处理缺失值和异常值。
2. **缺勤预测**：输入员工信息，输出缺勤概率（0-1之间）。
3. **数据库支持**：支持将预测结果保存到MySQL数据库，方便后续分析。

## 如何使用
1. **安装依赖**：
   ```bash
   pip install pandas scikit-learn mysql-connector
   ```

2. **预测示例**：
   ```python
   from absenteeism_module import AbsenteeismPredictor

   new_data = {'Transportation_expense': 250, 'Daily_work_load': 210, 'Education': 2}
   predictor = AbsenteeismPredictor('model.pkl', 'scaler.pkl')
   probability = predictor.predict(new_data)
   print(f"缺勤概率：{probability:.2%}")
   ```

3. **保存结果**：
   预测结果可以保存到MySQL数据库，方便后续使用。

## 文件说明
- **Absenteeism_data.csv**：原始数据，未处理的员工数据。
- **Absenteeism_preprocessed.csv**：清洗后的数据。
- **Logistic Regression.ipynb**：模型训练代码。
- **intergration.ipynb**：实际应用示例。
- **absenteeism_module.py**：数据预处理和预测工具。
- **model.pkl**：训练好的模型。
- **scaler.pkl**：数据标准化工具。

## 贡献与反馈
欢迎提交Issue反馈问题，或通过Pull Request贡献代码。项目采用MIT许可证，自由使用和修改。

## 示例结果
| 年龄 | 通勤费用 | 工作量 | 教育程度 | 预测概率 |
|------|----------|--------|----------|----------|
| 32   | 300      | 205    | 3        | 65.2%    |
| 28   | 150      | 198    | 1        | 18.7%    |
