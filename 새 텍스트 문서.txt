#include <stdio.h>

int main() {
	int arr[3][6] = { 0 }; //초기화 해야 합계와 평균값이 제대로 나옴 **중요**
	int i = 0, k = 0;

	printf("학번과 세 과목의 점수를 차례대로 입력하세요 : \n");

	for (i = 0; i < 3; i++) {
		for (k = 0; k < 4; k++) {
			scanf_s("%d", &arr[i][k]);
			if (k >= 1) {  //조건문 써야지 합계에 학번값이 안 들어갑니다 ㅠㅠ
				arr[i][4] += arr[i][k];
			}
		}
		arr[i][5] = arr[i][4] / 3.0;
	}

	printf("학번\tC_LANG\tInfo\tJava\t합계\t평균 \n");

	for (i = 0; i < 3; i++) {
		for (k = 0; k < 6; k++) {
			printf("%d \t", arr[i][k]);
		}
		printf("\n");
	}
}