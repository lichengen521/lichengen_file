import pytest
import allure
@pytest.fixture(autouse=True)
def before():
    print('函数开始前执行')

    yield 200

    print('执行结束后执行')
@allure.feature('普通方法实现')
@allure.story('能够在报告里显示')
@allure.step('第一步')
@pytest.mark.parametrize('num1',[1,2,3])
def test_a(num1):
    with allure.step('第一个函数'):
        print(f'参数是{num1}')

def test_b():
    print('正在执行b')
@pytest.mark.xfail(condtion=True,reason='不报错但是断言失败')
@allure.step('第二步')
@allure.severity('blocker')
def test_c():
    print('正在执行c')
    allure.attach('断言不是0')
    assert 0


if __name__ == '__main__':
    pytest.main(['-s', 'test_allure.py'])