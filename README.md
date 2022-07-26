# score-and-grade
# c programming
# Let's write struct programming that uses dynamic memory to represent grades! 동적 메모리를 이욯해서 성적을 나타내는 구조체 프로그래밍을 작성해보자!
#include <stdio.h>
#include <stdlib.h> //malloc(),free(),exit()
struct course{
	char subject[30]; //과목  
	double marks; //학점  
};
int main(void){
	int N;
	struct course *M;
	int i;
	printf("구조체의 개수: ");
	scanf("%d",&N);
	M=(struct course*)malloc(sizeof(struct course*)*N);
	if(M==NULL){
		printf("메모리 할당오류");
		exit(1);
	}
	for(i=0;i<N;i++){
		printf("과목이름과 성적 입력:");
		scanf("%s%lf",&M[i].subject,&M[i].marks);
	}
	printf("저장된 정보를 출력:\n");
	for(i=0;i<N;i++){
		printf("%-10s %lf\n",M[i].subject,M[i].marks);
		free(M);
	}
	return 0;
}
#result--> 구조체 개수: 1  과목이름과 성적입력: c언어 4.0  저장된 정보출력:  c언어 4.0000000
