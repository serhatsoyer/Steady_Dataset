# Steady_Dataset
<br/>
## Related Python Function to Download:
<br/>
def load_steady_dataset(file_name):<br/>
&nbsp;data = pd.read_csv(file_name)[1200:-300]<br/>
&nbsp;gyro_data = gyro_multiplier * data[['gyroRotationX', 'gyroRotationY', 'gyroRotationZ']].values<br/>
&nbsp;acc_data = data[['motionUserAccelerationX', 'motionUserAccelerationY', 'motionUserAccelerationZ']].values<br/>
&nbsp;pos_data = np.zeros((acc_data.shape[0], 3))<br/>
&nbsp;ori_data = np.ones((acc_data.shape[0], 4))<br/>
&nbsp;ori_data[:, 1:] *= 0<br/>
<br/>
&nbsp;return gyro_data, acc_data, pos_data, ori_data<br/>
<br/>
## File Seperation:
<br/>
for file_number in [1, 2, 5, 6, 7, 8, 11, 12, 13, 14, 15, 17, 18, 19, 22, 23, 24, 25, 26, 27, 28]:<br/>
&nbsp;imu_steady_filenames_train.append(dataset_address + 'steady/' + str(file_number) + '.csv')<br/>
<br/>
for file_number in [3, 9, 20]:<br/>
&nbsp;imu_steady_filenames_val.append(dataset_address + 'steady/' + str(file_number) + '.csv')<br/>
<br/>
for file_number in [4, 10, 16, 21]:<br/>
&nbsp;imu_steady_filenames_test.append(dataset_address + 'steady/' + str(file_number) + '.csv')
