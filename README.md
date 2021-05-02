# Steady_Dataset

## Related Python Function to Download:

def load_steady_dataset(file_name):
    data = pd.read_csv(file_name)[1200:-300]
    gyro_data = gyro_multiplier * data[['gyroRotationX', 'gyroRotationY', 'gyroRotationZ']].values
    acc_data = data[['motionUserAccelerationX', 'motionUserAccelerationY', 'motionUserAccelerationZ']].values
    pos_data = np.zeros((acc_data.shape[0], 3))
    ori_data = np.ones((acc_data.shape[0], 4))
    ori_data[:, 1:] *= 0

    return gyro_data, acc_data, pos_data, ori_data
    

## File Seperation:

for file_number in [1, 2, 5, 6, 7, 8, 11, 12, 13, 14, 15, 17, 18, 19, 22, 23, 24, 25, 26, 27, 28]:
    imu_steady_filenames_train.append(dataset_address + 'steady/' + str(file_number) + '.csv')

for file_number in [3, 9, 20]:
    imu_steady_filenames_val.append(dataset_address + 'steady/' + str(file_number) + '.csv')

for file_number in [4, 10, 16, 21]:
    imu_steady_filenames_test.append(dataset_address + 'steady/' + str(file_number) + '.csv')
